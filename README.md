## LED실험 R,G,B값을 받기 위해 만든 회로해석

----
![KakaoTalk_20240805_103348827_01](https://github.com/user-attachments/assets/896b11b2-b7b8-458f-a059-dafd14c22ee1)
![KakaoTalk_20240805_103348827](https://github.com/user-attachments/assets/64318bc3-e90c-490f-ae3a-8b2cdb3572c0)
![KakaoTalk_20240805_103441206](https://github.com/user-attachments/assets/8b6a9472-504e-411c-b0ea-3cb95ecd25f1)


### R,G,B 선에 연결 하고 깜빡깜빡 하는 주기의 신호값이 읽혀지는데 반전 증폭기 회로의 Gain은 -(R2/R1)이다. <br>
### 이를 통해 얼마만큼 증폭이 되는지 알 수 있고 LMC6484 증폭기의 1번에서 나온 출력이 5번 입력 전압으로 들어가게 되고 나오게 된 출력이 제너 다이오드로 전다. <br>

### 제너 다이오드는 본래 일정 전압을 받게 되면 역방향으로 동작하게 되어 정전압을 발생시키는데 순방향으로 껴주고 일정전압을 흘려보내지 않으면 그냥 다이오드의 역할을 하게 된다.(한 방향으로 전류를 흐르게 해주는 역할) <br>

### 반전 증폭기를 사용하는 이유로는 비반전을 사용하였을 때 입력 임피던스에 따라 발생하는 노이즈나 리플이 심해 측정중 잘못된 값이 기입될 수 있기에 보다 안정성이 높은 반전 증폭기를 선택 <br>

### 제너 다이오드를 통해 흐르는 전류는 각 커패시터에 저장되어 있다가 전류가 흐르지 않는 타이밍에 MOSFET에 전류를 흘려 보내주어 항시 출력값을 유지한다.(MOSFET은 전류의 양을 조절하는역할) <br>

### 아두이노로부터 신호를 받고 측정을 하게되면 신호선에서 gate에 일정한 전류를 흘려보내고 gate에서부터 동작을 하게 되면서 각각 2k, 1k에서 R,G,B값을 측정하고 측정된 값을 아래의 트랜지스터에 보내어 추출할 수 있다. <br>

### 맨 아래의 주황 타원은 '레귤레이터'로써 15V를 인가하였을 때 5V로 조절하여 전압인가를 하는 역할이다. <br>

### 위의 내용을 학습하기까지 참고한 사이트 : https://m.blog.naver.com/durian0328/222201280017, https://pdf1.alldatasheet.com/datasheet-pdf/view/9122/NSC/LMC6484IN.html, https://circuit-designer.tistory.com/entry/%ED%9A%8C%EB%A1%9C-%EA%B8%B0%EC%B4%88-%EB%B9%84%EB%B0%98%EC%A0%84-%EC%A6%9D%ED%8F%AD%EA%B8%B0%EC%97%90-%EB%8C%80%ED%95%B4-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90, 
https://blog.naver.com/bruno_annie/220767601583?photoView=2
