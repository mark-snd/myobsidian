2021-11-08 현재  
어제 Fan을 완전 분리하여 깨끗하게 청소했다. CPU온도가 50도 근처로 매우 낮다.  
따라서, Fan 소리는 나지 않는다.  
위와 더불어 전원 옵션에서 최대 프로세서 상태를 100%에서 80% 바꾸는 것도 해야 한다.  
CPU 온도는 CPUID HWMonitor 라느 프로그램을 깔아서 확인한다.
 
아래 글은 소용없음  
In order to try to reduce the noise from the NUC, we can try to set the fan to quiet, you just need to enter the BIOS, select “==Advanced==” then look for the “==Cooling==” tab and select “==Quiet==”. I test the Intel® NUC7I7BNH in our lab and I noticed there is a noise difference when the fan is set on quiet.
 
Intel Community 에 있는 사람이 제공한 아래 세팅으로 해결

![[Exported image 20260428061649-0.png]]

Petrous 라는 친구의 설명  
And the fan is always running but not very fast.  
And when the T° goes up to 80°C, the fan 'll accelerate by 4% each time. Until the T° goes down.