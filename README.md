# JamsilBridgeWar
![교류회 템플릿_잠실대교_1](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/c87add65-972e-4b6a-afe1-5a6af1164aad)
  
  
  
## 1. 게임개요
**1-1) 제목** : 잠실대교는 왜 막히는거야  
**1-3) 장르** : RTS(Real Time Strategy), 실시간 전략게임  
**1-2) 타깃 플랫폼** : Windows OS PC  
**1-3) 스토리적 배경**  
: ‘건대연합’은 잠실과 건국대  인근을 잇는  다리의 이름이 ‘건국대교’가 아닌 ‘잠실대교’인 것에 불만을 가지고 있었다.   
결국 ‘건대연합’이 잠실대교의 명명권을 얻기 위해 ‘잠실연합’에게 전쟁을 선포하게 된다.   
전쟁의 주 원인인 잠실대교가 전투의 장소가 되었고 이로 인해 잠실대교의 통행이 원활하지 않게 되었고,   
이를 모르는 사람들은 뚫리지 않는 잠실대교를 바라보며 ‘잠실대교는 왜 막히는거야’라며 푸념을 늘어놓는다.  
( 스토리 영상 : https://www.youtube.com/watch?v=uk5n8rE756s )  
**1-4) 지리적 배경**  
: 잠실대교 인근의 실제 지형을 사용하며 북쪽으로는 건국대학교 일감호, 남쪽으로는 석촌호수를 포함한다.  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/06b9f480-a2c0-4bea-b514-aa61fa85d936)  

구현과정에서 건물들을 간략화하고, 특징이 될 수 있는 건물들과 Object로써 활용할 건물 위주로 구성.  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/39cc51b1-7bbf-43d1-a3b3-1a8300adff27)
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/79d1ed2a-b25b-4ca6-ba01-3e76703f2c53)

**1-5) 게임종료 조건**  
: 각 진영 요새 중 어느 한 곳이라도 파괴되는 경우 게임이 종료된다.   
건대 요새의 파괴되면 플레이어의 승리, 반대는 AI의 승리가 된다.  
  
  
  
## 2. 게임유닛
**2-1) 건물 유닛 및 오브젝트**  
● 잠실대교  
잠실대교는 지상유닛이 상대 진영으로 넘어갈 수 있는 유일한 통로로, 두 진영의 지상유닛 간의 주된 전투지역으로 활용된다.  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/f2e21f24-7b3c-49fe-a97e-003f0dd04c78)

● 요새(육군기지)  
건대진영은 가상의 건국대학교 건물, 잠실진영은 롯데월드를 사용하며, 지상유닛을 소환할 수 있다.   
- 업그레이드 : 지상유닛의 공격력 및 요새의 HP증가, 요새에 공중유닛 공격시스템 추가  
  ![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/6318dfd0-7846-4334-92a2-26cca8aa74cf)

● 해군기지  
건대진영은 일감호, 잠실진영은 석촌호수에 위치하며 수중유닛을 생산할 수 있다  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/64ece7e3-dbd7-4efd-944b-77a635bad1e8)

● 공군기지  
건대진영은 스타시티, 잠실진영은 롯데타워에 위치하며 공중유닛을 생산할 수 있다.  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/ed2b9f00-afd1-405a-967b-9426196743ec)

● 꽃밭  
꽃밭에서는 춤추기 애니메이션을 동반한 상호작용을 통해 골드수급이 가능하다.  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/0772b2bc-7b4e-4437-b940-5d5e830e8f27)

**2-2) 캐릭터 유닛**  
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/7891d670-a6ac-40fe-a149-056faaaae789)  
● 지상 유닛  
지상유닛은 근거리와 원거리 유닛으로 나뉘며, 육로로는 오직 잠실대교를 통해서만 상대 진영으로 이동이 가능   
● 수상 유닛  
수상유닛은 적 진영에 위치하는 상륙지점에 도달하는 경우에 남은 HP에 비례하여 근접 지상유닛으로 변환.   
● 공중 유닛  
공중유닛은 열기구에서 달걀을 던지는 형식으로 공격하며, 상대 요새에 대한 타격이 불가능  
  
  
  
## 3. 게임플레이 
**3-1) 시점**
: 기본적으로 탑뷰 시점을 활용하며, 마우스와 키보드의 움직임에 따라 맵 내에서는 자유롭게 이동이 가능하다.  
**3-2) UI**
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/9b924066-4b6c-4182-900e-0e6647ce6328)
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/978c1d97-5d91-4661-90f4-e1e9dc6b2ef0)
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/59c79e3f-8e71-4559-924c-b707fcaaf90d)
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/14205440-b924-4f86-8958-11047a8192b0)
![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/dd1f8e02-d11f-4295-ad1c-6b99b4a4aa29)

**3-3) 골드 획득**
: 기본적으로 일정 시간마다 골드를 획득하며, 지상유닛이 ‘Club’에서 상호작용하여 추가적으로 골드를 획득할 수 있다.  
**3-4) 게임 조작방법**
● 공통    
- 유닛은 개별이동 및 드래그를 이용한 다수선택으로 군집으로 이동이 가능     
- 선택된 유닛(혹은 군집)은 마우스 우클릭 지점으로 이동    

● 유닛 생성방법    
- 유닛은 각각 기지의 지정된 스폰장소에서 스폰    
- 유닛을 생성하는 UI는 각각 해당되는 기지를 더블클릭하여 화면에 표출하며 UI에서는 어떤 유닛을 얼마나 생성할지 선택이 가능    
 ![image](https://github.com/grace7040/JamsilBridgeWar/assets/81251069/3a600c3e-7a06-46cd-8ce6-462a2d22c8d3)

**3-5) 전투방식**    
● 공통  
컨트롤 하고있는 유닛(혹은 군집)이 있을때 상대 유닛(군집)의 인근으로 유닛을 이동시키면 적을 인식하여 스스로 전투를 시작하며,   
전투중에도 플레이어의 이동 커맨드가 주어지면 전투를 멈추고 이동     
● 지상유닛  
지상유닛은 근거리와 원거리로 구분하며, 지상유닛은 오직 지상유닛에게만 타격이 가능   
● 수상유닛  
수상유닛 역시 지상유닛이나 공중유닛 타격이 불가능하며, 수상유닛간의 공격만 가능   
● 공중유닛  
공중유닛은 공중유닛을 제외 모든 유닛의 타격이 가능하며,업그레이드된 요새의 공격만 공중유닛 타격이 가능  



