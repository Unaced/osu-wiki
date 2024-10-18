# lazer로 업그레이드

osu!(lazer)는 osu!의 다음 메이저 업데이트입니다. osu!의 시스템을 정확히 재구현하기 위해 수년간의 노력을 들인 결과물입니다.  

lazer의 최종 목표는 기존의 스테이블 버전을 완전히 대체하는 것입니다. 하지만 여전히 미완성된 부분이 존재하고, 스테이블 유저들이 전부 넘어오기 전까지는 스테이블을 계속 지원할 예정입니다.

"lazer"는 임시로 정한 코드네임이며 정식 출시 이후에는 lazer라는 명칭을 사용하지 않을 예정입니다. 이 문서에서는 이해를 돕기 위해 osu!(lazer)는 lazer로, osu!(stable)은 스테이블로 칭합니다.

## 기능 비교

*게임 플레이에서의 차이점에 대해서는 [Gameplay differences in osu!(lazer)](/wiki/Client/Release_stream/Lazer/Gameplay_differences_in_osu!(lazer))를 참고하시기 바랍니다.*

아래 표는 현재 lazer 버전과 스테이블 버전의 차이점을 설명합니다. 최종 목표는 시간이 지남에 따라 플레이어가 원하는 모든 기능을 구현하는 것입니다.

### 호환성 및 성능

| 기능 지원 | 스테이블 | lazer |
| :-- | :-- | :-- |
| Windows 8.0 이하 | ![Yes][true] | ![No][false] |
| macOS / Linux | ![Partial][partial][^wine] | ![Yes][true] |
| DirectX / Metal | ![Partial][partial][^compatibility-mode] | ![Yes][true] |
| 모바일 지원 | ![No][false] | ![Yes][true] |
| 멀티스레드 아키텍처 | ![No][false] | ![Yes][true] |
| 비디오 하드웨어 가속 | ![No][false] | ![Yes][true] |
| UI 크기 조정 | ![No][false] | ![Yes][true] |
| 커스텀 게임 모드 | ![No][false] | ![Partial][partial][^dll] |
| 중복 파일 방지 | ![No][false] | ![Yes][true][^share-files] |
| 타블렛 인식 면적 조정 | ![No][false] | ![Yes][true] |
| 다양한 화면 비율 지원 | ![No][false] | ![Yes][true] |

### UI 및 스킨

| 기능 지원 | 스테이블 | lazer |
| :-- | :-- | :-- |
| 스킨 사용 가능 | ![Yes][true] | ![Partial][partial][^gameplay-only] |
| 노래 선택 그룹화 | ![Yes][true] | ![No][false] |
| 게임 내에서 스킨 및 UI 레이아웃 조정 | ![No][false] | ![Yes][true] |
| 커스텀 가능한 동적 스킨 요소 | ![No][false] | ![Yes][true] |

### 인터페이스

| 기능 지원 | 스테이블 | lazer |
| :-- | :-- | :-- |
| 메인 메뉴에서 스토리보드 표시 | ![No][false] | ![Yes][true][^supporter] |
| 난이도 숨기기 | ![No][false] | ![Yes][true] |
| 최초 실행 설정 마법사 | ![No][false] | ![Yes][true] |
| 논리 삭제(Soft delete) | ![No][false] | ![Yes][true][^soft-deletion] |
| 게임 플레이 중 설정 실시간 적용 | ![No][false] | ![Yes][true] |

### 게임플레이

| 기능 지원 | 스테이블 | lazer |
| :-- | :-- | :-- |
| 정확한 퍼포먼스 포인트 계산 | ![Partial][partial][^online] | ![Yes][true] |
| 난이도 조정 | ![No][false] | ![Yes][true][^difficulty-adjust] |
| 모드 프리셋 | ![No][false] | ![Yes][true] |
| 개별 모드 조정 | ![No][false] | ![Yes][true] |
| 재미를 위한 모드 | ![No][false] | ![Yes][true] |
| 콤보 색상 일반화[^normalisation] | ![No][false] | ![Yes][true] |
| 홀드로 HUD 표시 | ![No][false] | ![Yes][true][^hold-for-hud] |
| 개별 비트맵마다 오프셋 조정 | ![Partial][partial][^offset-calibration-stable] | ![Yes][true][^offset-calibration-lazer] |
| 움직이는 슬라이더 | ![No][false] | ![Yes][true][^can-disable] |
| 유저에게 친화적인 노트락 기능 | ![No][false] | ![Yes][true][^note-lock] |
| osu!mania와 osu!에서 타이밍 기반 노트 색상 적용 | ![No][false] | ![Yes][true] |
| 리플레이 탐색 | ![No][false] | ![Yes][true] |
| [니코동](https://en.wikipedia.org/wiki/Niconico) 스타일의 리플레이 댓글 기능 | ![Yes][true] | ![No][false] |

### 온라인 시스템

| 기능 지원 | 스테이블 | lazer |
| :-- | :-- | :-- |
| 점수 등록 | ![Yes][true] | ![Yes][true] |
| 비트맵 순위표 | ![Yes][true] | ![Yes][true] |
| 프로필 통계 | ![Yes][true] | ![Yes][true] |
| 메달 | ![Yes][true] | ![Partial][partial][^medals-lazer] |
| 퍼포먼스 포인트 | ![Yes][true] | ![Yes][true] |
| 실시간 채팅 | ![Partial][partial][^stable-chat] | ![Yes][true] |
| 위키 / 뉴스 / 변경 사항 / 랭킹 | ![No][false] | ![Yes][true][^online-content] |
| 유저 프로필 | ![No][false] | ![Yes][true] |
| 인게임에서 비트맵 다운로드 | ![Partial][partial][^direct-supporter] | ![Yes][true] |
| 인원 제한 없는 멀티 방 | ![No][false][^multi-room-max] | ![Yes][true] |
| 멀티 관전 | ![No][false] | ![Yes][true] |
| 카운트다운 타이머 | ![Partial][partial][^countdown-timers-stable] | ![Yes][true][^countdown-timers-lazer] |
| 대기열 모드 | ![No][false] | ![Yes][true][^queue-modes] |
| 멀티 커맨드 | ![Yes][true] | ![No][false] |
| TAG co-op | ![Yes][true] | ![No][false] |
| 플레이리스트 | ![No][false] | ![Yes][true] |
| 비트맵 실시간 업데이트 | ![Partial][partial][^map-only] | ![Yes][true][^all-files] |

### 에디터

| Feature | stable | lazer |
| :-- | :-- | :-- |
| osu! editor | ![Yes][true] | ![Yes][true] |
| osu!taiko editor | ![No][false] | ![Yes][true] |
| osu!catch editor | ![No][false] | ![Yes][true] |
| osu!mania editor | ![Yes][true] | ![Yes][true] |
| 참고용으로 비트맵의 다른 난이도 열기 | ![Yes][true] | ![No][false] |
| 오브젝트별 슬라이더 벨로시티 / 볼륨 | ![No][false] | ![Yes][true] |
| 세그먼트별 슬라이더 커브 유형 | ![No][false] | ![Yes][true] |
| 슬라이더 분할 및 병합 | ![No][false] | ![Yes][true] |
| 패턴 회전 | ![Yes][true] | ![Yes][true] |
| 패턴 크기 조절 | ![No][false] | ![Yes][true] |
| 비트맵 업로드 | ![Yes][true] | ![No][false] |
| 스토리보드 편집기 | ![Yes][true] | ![No][false] |
| 상호호환 | ![Yes][true] | ![Partial][partial][^incompatibilities] |

## lazer로 전환하기

lazer를 사용해 보기로 결정하셨나요? 좋습니다!

[여기](https://osu.ppy.sh/home/download)에서 다운로드할 수 있습니다. 조만간 스테이블에서 lazer로 바로 업데이트할 수 있는 선택지도 주어질 예정입니다.

## 자주 묻는 질문

### 이주

#### 스테이블은 버려질 예정인가요? 나중에는 무조건 스테이블을 버리고 갈아타야 하나요?

사람들이 스테이블을 계속 사용하는 한 스테이블은 계속 유지될 예정입니다. 적어도 수 년간은 유지될 겁니다. 

#### 스테이블에서 lazer로 모든 데이터를 이전할 수 있나요?

현재는, 비트맵, 스킨, 점수, 리플레이, 컬렉션이 lazer로 이전 가능합니다. 참고로, **설정값은 이전되지 않습니다**.

#### lazer로 비트맵을 불러오면 디스크 용량을 두 배로 차지하게 되나요?

lazer와 스테이블을 같은 디스크에 설치했다면, [하드 링크](/wiki/Client/Release_stream/Lazer/File_storage#via-hard-links)가 사용되어 불필요한 디스크 사용을 방지합니다.

같은 디스크가 아니라면, 디스크 용량을 두 배로 차지하게 됩니다.

#### lazer를 삭제하면 스테이블이 망가지나요?

아니요.

#### 스테이블을 삭제하면 lazer가 망가지나요?

아니요.

#### lazer를 설치했다가 다시 스테이블로 돌아갈 수 있나요?

네, lazer는 항상 스테이블과 함께 설치됩니다. 둘 중 하나를 삭제하지 않는 한 둘 다 액세스할 수 있습니다.

#### lazer에서 스테이블로 데이터를 이전할 수 있나요?

아니요. 이 기능은 지원되지 않을 예정입니다.

하지만 현재로서는 개별 스코어와 비트맵을 lazer에서 내보내고 스테이블로 수동으로 가져올 수 있습니다.

### 게임플레이 및 스코어링

#### lazer에서 점수를 달성해도 프로필애 표시되나요?

네, 단 웹사이트에서 "lazer 모드"가 꺼진 상태라면 "최고 성과"란에는 점수가 표시되지 않습니다.

또한 현재로서는 설정과 관계없이 '1위 달성 맵'란에도 표시되지 않습니다.

#### lazer에서 퍼포먼스 포인트를 얻을 수 있나요?

네.

#### lazer는 ScoreV2를 사용하나요?

ScoreV2에 기반하여 개편된 스코어링 시스템을 사용합니다.

<!-- lint ignore no-heading-punctuation -->

#### 전 옛날처럼 점수값이 크게 나오는게 더 좋은데, 변경할 수 있나요?

설정에서 `점수 표시 모드`를 `클래식`으로 변경하면 옛날처럼 점수값이 크게 나오게 됩니다. 점수가 약간 부정확할 수 있지만 그 느낌을 다시 살릴 수는 있습니다.

글로벌 순위표에서도 클래식 점수 표기가 적용됩니다.

#### lazer에서 점수를 달성하면 영원히 남게 되나요?

저희는 가능한 한 점수를 보존하기 위해 노력하고 있지만, **영원히 남는다는 보장은 못합니다.** 예를 들면 부정 행위가 발견될 경우 형평성을 위해 점수를 싹 없애버릴 수도 있습니다.

#### 스테이블에서 달성한 점수가 lazer에도 표시되나요?

네.

#### lazer에서 달성한 점수가 스테이블에도 표시되나요?

현재는 안됩니다.

#### 모드 선택에 상관없이 Ranked 플레이가 가능한가요?

순위표에는 모드 선택에 상관없이 점수가 올라가게 됩니다.

단 현재로서는 아래의 모드를 선택한 경우에만 퍼포먼스 포인트가 지급됩니다.

- 난이도 감소
  - Easy
  - No Fail
  - Half Time (only 0.75x, configuring `Adjust pitch` is allowed)
  - Daycore (only 0.75x)
- 난이도 상승
  - Hard Rock (not for osu!mania)
  - Sudden Death (Configuring `Restart on fail` is allowed)
  - Perfect (Configuring `Restart on fail` is allowed)
  - Hidden
  - Nightcore (only 1.5x)
  - Double Time (only 1.5x, configuring `Adjust pitch` is allowed)
  - Flashlight
  - Blinds
  - Accuracy Challenge
- 변환 (osu!mania 전용)
  - 미러
  - 4K
  - 5K
  - 6K
  - 7K
  - 8K
  - 9K
- 재미
  - Muted
  - No Scope
- 자동화 (osu! 전용)
  - Spun out
- 시스템
  - 터치 디바이스

위에 달리 명시되지 않는 한, 모드의 기본 설정으로만 퍼포먼스 포인트를 받을 수 있습니다.

#### 새로운 게임플레이 방식이 마음에 안 드는데, 스테이블 같은 옛날 방식으로 돌아갈 수 있나요?

모드 선택에서 "클래식" 모드를 사용해 보세요. 익숙했던 옛날 방식으로 플레이할 수 있습니다. 또한 클래식 모드의 커스터마이즈 탭을 확인해 보세요. 값을 자신에 맞게 조정하거나 무엇이 바뀌는지 볼 수 있습니다.

### 스킨 및 UI

#### Something is behaving differently to stable and I don't like it!

Please run the setup wizard at the top of settings and go through the settings on the `Behaviour` screen. A lot of the common settings which have defaults changed are listed here. There's also a single button you can press to apply the old behaviours as a starting point for your lazer journey.

#### 노래 선택 메뉴랑 결과창 화면이 바뀌는 스킨도 작동할 예정인가요?

가능한 한 새로운 기능들을 막지 않으면서 스킨이 적용되도록 최선을 다하고 있습니다. 이 기능은 나중에 나올 예정입니다.

#### 메뉴에서도 커서 스킨이 작동할 예정인가요?

이는 요청이 많았던 기능이기에 언젠가는 가능할 예정입니다.

### 성능

#### 왜 최대 FPS를 무제한으로 설정할 수 없게 한건가요?

일정 수치 이후로는 더 높은 프레임으로 구동할 이유가 없습니다. Lazer는 다양한 신기술이 적용되어 프레임이 높지 않아도 낮은 지연율을 달성할 수 있습니다. 이는 저희가 더 많은 기능을 구현함에 따라 더 발전할 것입니다.

Lazer는 FPS 리미터에 상관없이 입력을 1000Hz로 폴링하기 때문에, 최대 FPS를 1000 이상으로 설정할 이유가 없습니다.

FPS가 입력 지연 시간에 어떤 영향을 미치는지 궁금하다면 설정 하단에 내장된 '지연 시간 인증기'를 실행해 보세요.

또한 이 [기술 문서](https://github.com/ppy/osu/wiki/Latency-and-unlimited-frame-rates)에는 우리가 가고자 하는 길과 그 근거를 설명하고 있습니다.

#### 입력을 1000Hz로 폴링하는 거면, 제 8000Hz 게이밍 마우스는 의미 없는 건가요?

운영 체제는 여전히 더 높은 값으로 폴링하긴 하지만, 이로 인한 이점은 거의 없는 수준입니다. 이렇게 높은 속도로 폴링하면 예기치 않은 오버헤드가 발생할 수 있으므로 시스템 안정성을 위해 장치를 1000Hz로 제한하는 것이 좋습니다.

#### 전 Lazer가 스테이블보다 불안정하던데 왜일까요?

대부분의 최신 하드웨어에서는 Lazer가 안정적인 성능을 보이지만, 사용자마다 하드웨어 구성이 다른 경우에는 항상 예외적인 경우가 있습니다. 저희의 단기 로드맵에서는 모든 하드웨어에서 OpenGL보다 드라이버 지원이 우수한 DirectX(일명 '호환 모드')와 Vulkan을 지원하는 것을 목표로 하고 있습니다. 이 기능이 구현되면 인텔 내장그래픽과 같은 하드웨어의 성능이 크게 향상될 것입니다.

### 피드백 전송

#### 원래 쓰고 있던 기능이 안보여요! / ~가 바뀌였는데 마음에 안들어요 / 버그를 발견했는데 어떻게 신고해야 하나요?

There's a very high chance we are already aware of this and tracking it for future implementation! Please search the [issue tracker](https://github.com/ppy/osu/issues) and [discussions page](https://github.com/ppy/osu/discussions). If you can't find any matching threads, feel free to [open a discussion](https://github.com/ppy/osu/discussions/new).

Do note that we are already tracking over 1,000 issues of varying priorities, and it may take us some time to fix issues that only affect a small number of users.

### 기타

#### 왜 "lazer"라고 부르는 건가요?

커팅 엣지보다 더 날카로운건 뭘까요?

#### 정식 출시까지 왜이리 오래 걸리는 건가요?

osu!는 단순한 게임처럼 보이지만, 수백 가지의 기능과 시스템으로 구성되어 있습니다. 보는 사람에 따라서는 몇 년 전부터 완전히 플레이 가능한 상태였을 수도 있고, 수많은 기능이 누락된 상태 였을 수도 있습니다.

또한 저희는 역사 보존에도 많은 노력을 기울여 원래 계획에 없던 예외 사항들을 포함하여 비트맵이 정확하게 작동하도록 하고 있습니다. osu!는 유저들은 계획된 범위를 훨씬 넘어 게임을 자유롭게 확장해 왔으며 앞으로도 이를 포용하고 지원하기 위해 최선을 다하고 있습니다.

마지막으로, 저희는 코드 기반이 향후에도 잘 활용될 수 있도록 시간과 노력을 기울이고 있습니다. 앞으로 새로운 기능을 빠른 속도로 온라인에 적용할 수 있도록 기초 작업을 마쳤습니다. 여기에는 새로운 UI 구성 요소, 새로운 게임 스킨, 새로운 멀티플레이어 시스템이 포함되며, 완전히 새로운 게임 모드(일명 룰셋)에서 기존의 모든 비트맵을 로드하고 플레이할 수 있는 기능도 추가될 예정입니다!

#### 향후 계획은 뭔가요?

사용자가 요청하는 기능과 개선사항에 대한 백로그가 엄청나게 쌓여 있으며, 빛의 속도로 계속 추진해 나갈 예정입니다. 최근에 가입했지만 아직 osu! 개발의 추진력을 경험하지 못한 분들은 깜짝 놀랄 준비를 하세요.

#### 노래 폴더는 어디에 있나요?

Lazer에는 노래 폴더가 없습니다! 덕분에 노래 선택 시 `F5`를 눌러 비트맵을 새로 고칠 필요가 없고(비트맵은 항상 좋은 상태이므로) 비트맵이 사용하는 디스크 공간을 20~40%까지 줄일 수 있는 등의 멋진 작업을 할 수 있습니다. 자세한 내용은 [레이저가 파일을 저장하는 방식](/wiki/Client/Release_stream/Lazer/File_storage)을 참고하세요.

비트맵을 변경해야 하는 경우 에디터를 사용해 주세요. 앞으로 편집기에 외부 편집을 위해 일시적으로 비트맵 폴더에 액세스할 수 있는 모드를 도입할 예정입니다. 이렇게 하면 비트맵을 만드는 과정에서 외부 도구를 사용할 수 있습니다.

#### 이제 모든 플레이어가 "osu!direct"를 사용할 수 있는데, 기존 서포터에게는 특별한 혜택이 있나요?

비트맵 리스팅의 일부 필터는 여전히 서포터만 사용할 수 있습니다.

이미 몇 가지 추가적인 혜택도 있습니다:

- 서포터는 더 오래 재생되는 재생 목록을 만들 수 있습니다.
- 서포터는 메인 메뉴에서 스토리보드 재생을 활성화할 수 있습니다.

향후 새로운 혜택을 검토할 계획이지만, 현재는 안정적인 기능에 중점을 두고 있습니다. 게임 개발을 지원하려면 서포터 태그를 구매해 주세요!

#### lazer에서 부정 행위를 하면 밴을 당하나요?

네.

#### 만약 lazer에서 부정 행위를 발견하면 어떻게 신고해야 하나요?

원래 하던 대로 하시면 됩니다.

#### 소액결제는 어디에 있나요?

아마 다른 게임이랑 착각하신 거 같습니다.

## Notes

[^wine]: Wine을 통해서 가능.
[^compatibility-mode]: 호환 모드를 통해 DirectX 사용 가능.
[^dll]: `.dll` 파일을 직접 수정하여 가능.
[^share-files]: 비트맵과 스킨이 같은 파일을 사용하여 디스크 공간을 절약.
[^gameplay-only]: 게임플레이 전용. Gameplay only.
[^online]: Via online retrieval.
[^normalisation]: 서클의 색의 밝기를 표준화시킴. This brings beatmap custom combo colours to the same brightness level.
[^hold-for-hud]: Ctrl을 홀드하여 잠시 숨겨진 HUD를 볼 수 있음. Hold `Ctrl` to view the HUD momentarily while it's hidden.
[^offset-calibration-stable]: 키 할당을 변경하여 수동으로 조절 가능. Adjustable manually via key bindings.
[^offset-calibration-lazer]: 비트맵을 재시작할 때 마지막 플레이를 기반으로 오프셋 조정 가능. When retrying a beatmap, you can calibrate the offset based on your last play.
[^can-disable]: 비활성화 가능. Can be disabled.
[^note-lock]: 노트락 시스템 자체는 존재하지만, 더이상 플레이를 방해하지 않음. Still exists, but should not interfere.
[^online-content]: 대부분의 온라인 컨텐츠에 직접 액세스 가능. Native access to most online content.
[^direct-supporter]: osu!direct를 통해 가능(서포터 전용).
[^supporter]: 서포터 전용.
[^soft-deletion]: 설정에서 삭제한 데이터 복구 가능. 게임 재시작 시 복구 불가.
[^multi-room-max]: 최대 16명.
[^map-only]: 맵 전용. Map only.
[^all-files]: 모든 파일. All files.
[^incompatibilities]: 일부 에디터 기능 사용 시 스테이블에서 부정확하게 작동함 — 추후 수정 예정. Some editor features will cause beatmaps to play incorrectly in stable — will be fixed soon.
[^stable-chat]: 메시지 받기까지 최대 15초정도 소요.
[^countdown-timers-stable]: 커맨드로 카운트다운은 사용 가능하지만 자동 시작은 불가.
[^countdown-timers-lazer]: 게임 UI에서 카운트다운을 설정하여 매치 자동 시작 가능.
[^queue-modes]: 활성화 시 로비에 있는 모든 유저가 비트맵을 추가할 수 있음.
[^difficulty-adjust]: 난이도 조정 모드로 노래 선택 화면에서 CS/AR/OD/HP 조정 가능
[^medals-lazer]: 일부 [Hush-Hush 메달](/wiki/Medals#hush-hush)은 획득 불가.

[true]: /wiki/shared/true.png
[false]: /wiki/shared/false.png
[partial]: /wiki/shared/partial.png
