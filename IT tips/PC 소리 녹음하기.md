[Audacity](https://www.audacityteam.org/) 가 가장 확실하다  
다운로드는 검색하면 금방 찾을 수 있음
 
목적  
온라인 회의 내용 녹음하기
 
**보기에서** **장치** **Bar** **나오게** **하고**  
Windows WASAPI, 마이크는 현재 사용 중인 스피커(이어폰)의 loopback을 선택한다.

![[Exported image 20260428061203-0.png]]  

문제점  
회의 녹음할 때 내 목소리는 저장할 수 없다. Source는 1개만 선택할 수 있고 Source로 스피커(이어폰)를 선택하면 상대방 목소리만 녹음된다.
 
해결책  
OBS를 사용해야 화면, 내 목소리와 상대방 목소리 모두를 저장할 수 있다.
 
Question:  
I've tried this using zoom and I can only get audacity to either record my voice or the other speaker but not both at the same time. How do you get around this?
 
Answer:  
Short answer, use OBS to record multiple audio sources like: computer sound and your microphone. Audacity may work if you have 2 versions of audacity running at the same time, one for your microphone and the other for wasapi like in this video. OBS is free btw.