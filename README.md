# MIII-M3-
Music Make Meet / Mobile Application

#모바일 클라우드 제안서
MIII(Music Make, Meet)


#목차

1 어플리케이션 목적<br>
2 아키텍쳐 (Server, Client, DB)<bR>
3 구현 기능 및 구현 예정 기능<br>
4 예상 스케쥴 (Server, Client, DB)<bR> 
<br><br><br><br>



#어플리케이션 목적<br>
상황.1<br>
음악을 만드는 사람에게 있어서 고의든 실수든 음악 표절은 씻을 수 없는 치욕이다. 그렇다면 음악 표절을 막을 수 있는 방법은 없는 것인가?<br>
상황.2<br>
작곡을 취미로 하는 A는 만든 음악을 B에게 들려주었다. A는 평가를 기대 했지만 B는 어디서 많이 들어본 것 노래 인 것 같다며 A의 꿈을 짓누른다. 그렇다면 A가 기존의 노래와 같은 노래를 만든 것인지 알 수는 없을까?<br>
<br><br>
앞 선 상황을 통해 표절 시비는 음악인들에게는 가장 큰 골칫거리가 아닐 수 없다. 그래서 음악인들이 서로 만든 음악의 표절을 피하고 마음이 맞는 사람과 같이 작업도 하고 지식도 얻어 갈 수 있는 시스템이 있다면 해결 될 수 있겠다는 생각에 개발을 하게 되었다.<br>
<br><br>
#아키텍쳐(Server, Client, DB)

	Client (Android OS 기기)<br>
클라이언트는 안드로이드 OS 기반의 기기들로 설정하며 클라이언트에서 갖게 되는 무게를 가볍게 하기 위해 필수 기본 데이터 (사용자 정보)를 제외한 데이터는 서버에 저장한다. 클라이언트에서는 
	Server (Amazone)
아마존 서버에는 사용자의 정보, 사용자가 분석하고 싶어하는 음악과 분석을 했었던 음악들의 성향, 주기적으로 측정되는 위치, 다른 사용자와의 채팅 내용이 저장 된다.<br>
	Server (Bonacell)
아마존 서버에서 음원을 보내면 보나셀 서버에서 음원을 분석하여 분석결과와 비슷한 음원의 정보를 아마존 서버에 저장한다. <br>
	DB (RDB)
아마존 서버에서 사용할 DB는 RDB를 사용한다. Hadoop 사용시 추가적인  제약사항 때문에 많이 써본 RDB를 사용한다.  RDB 설계 시 릴레이션의 복잡도가 높지 않다고 판단되며 학습 시간 없이 바로 사용 할 수가 있다.<br>
<br><br>
#구현 기능 및 구현 예정 기능
MIII의 기능은 다음과 같습니다.<br>
	사용자의 위치를 주기적으로 서버에 등록한다.<br>
	같은 프로그램 사용자의 정보(음악 성향 등)를 보여주고 사용자가 다른 사용자에게 채팅 초대를 하고 다른 사용자가 수락 시 두 사용자는 채팅을 할 수 있다. (음악 제작을 같이 한다 던지, 친목 도모 등)<br>
	사용자가 음원(작곡 음원, 음악 악보, 기존 음원)을 등록하면 보나셀의 분석 툴을 이용하여 등록한 음원과 어디까지 비슷한지, 비슷한 음원이 무엇이 있는지를 사용자에게 보여준다.<br>
	분석 툴을 통하여 비슷한 음원이 없는 경우 사용자는  Needle Tagger의 변형 시스템을 이용하여 음원 정보를 등록 할 수 있다. 사용자가 등록 한 음원은 다른 사용자들이 들을 수 있도록 자동 공개 된다.<br>
MIII의 기술은 다음과 같습니다.<br>
	JSON 파싱을 통하여 서버통신을 구현한다.<br>
	구글맵과 GPS, Wifi, Networkf를 통하여 위치를 파악하고 보여주는 것을 구현한다.<br>
	 카카오톡 API를 이용하여 채팅 기술을 구현한다. <br>
	Needle Tagger를 분석하여 시스템을 재 활용한다.<br>
	 등록한 악보를 음원으로 변환하는 작업을 구현한다.<br>
	사용자가 등록하고 들은 음원들의 성향을 자세하게 나눈다.<br>
<br><br>
 #예상 스케쥴
2015-04-11 ~ 2015-05-03	디자인 설계 및 자료 수집<br>
2015-05-09 ~ 2015-05-17	Client UI 및 서비스 환경 구축 완료<br>
2015-05-23 ~ 2015-05-31	Client와 Server(Amazone) 간의 통신 구축 완료<br>
2015-06-06 ~ 2015-06-07	Server(Amazone)와 Server(Bonacell) 간의 통신 구축 완료<br>


