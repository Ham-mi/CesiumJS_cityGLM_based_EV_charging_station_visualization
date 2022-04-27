# CesiumJS 및 cityGLM 기반 전기차 충전소 시각화
CesiumJS_cityGLM_based_EV_charging_station_visualization

> 서론

탄소중립과 기후 위기에 따라 유럽에서는 2030년까지 1990년 대비 이산화탄소 배출량을 55% 감축하며 2050년에는 탄소의 순 배출량을 0으로 만드는 것을 목표로 하는 규제안인 Fit for 55를 발표하였다. 5) 유럽의 이러한 규제안으로 인해 친환경 미래 자동차에 대한 관심이 커지고 있어 2025년 노르웨이, 2030년 영국, 독일과 폭스바겐, 2035년 중국과 GM, 2040년 프랑스는 내연기관 차량의 생산을 중단하겠다고 선언하였다. 각국과 기업들의 내연기관 퇴출 선언과 맞물려 세계 전기 자동차 제조업체는 2016년 65개에서 2020년 149개로 229% 급증하며 세계적인 차량의 트렌드는 저탄소 미래 자동차로 전환 중이다. 

 1) 국제에너지기구(IEA)에 따르면 전기차 판매가 2020년에 2019년 보다 41% 증가하여 약 300만 대의 전기차가 판매되었다. 전체 자동차 시장 점유율은 1%에서 4.6%로 증가하였다. 2021년 상반기 전 세계 전기차 판매대수는 전년동기 대비 168% 급증해 256만 대가 판매되었다. 전년 연간 판매 대수 대비 80% 수준이다. 3) 

대한민국 정부도 온실가스 배출에서 많은 부분을 차지하는 수송 분야에서 내연기관 퇴출을 위해 전기차 보급 확대와 전기차 충전소 인프라 구축 정책과 투자를 추진 중이다. 2025년까지 20조 원 이상 전기차 등 그린 모빌리티에 투자하여 2025년 공용 전기차 급속 충전기 15,600기를 구축할 계획이며, 2030년 전기차 300만 대를 보급할 계획이다. 2)

하지만 국내 전기 충전소의 공급 부족으로 인해 전기차 보급 국가 정책에 악영향을 미치고 있다. 서울시의 승용차 통행자의 전기차 구매 장애 요인 설문 조사 결과 1순위가 충전소가 부족하다는 것이다. 국내 전기차 충전소는 사용량을 고려하지 않고 설치가 용이한 입지를 중점으로 설치되어 있어 실제 수요와는 달라 충전소 이용자들의 불편이 발생하고 있다..

문제를 해결하기 위한 도시 모델 데이터는 거대하고 복잡한 구조이며 이를 효율적으로 시각화 하는 시스템은 부족하다. 최근 수십 년 동안 컴퓨터 그래픽 하드웨어의 기능이 크게 향상되었지만 대규모 도시 모델 도면 기술의 실제 적용에는 여전히 많은 문제가 있다. 3D 도시 시뮬레이션 기술은 GIS, 3D 시뮬레이션 분야의 공통 관심사 중 하나이다. [1]  본 연구에서는 전기차 충전소의 신규 설치 장소의 최적의 입지 장소를 효율적으로 시각화 하는 것이 목표이다.


> 연구 단어 정의

**Vworld** : 국가가 보유하고 있는 공개 가능한 모든 공간정보를 점진적으로 국민에게 제공하는 공간정보 오픈플랫폼 <br>
**WebGL** : 웹 기반의 그래픽 라이브러리. 자바스크립트 프로그래밍 언어를 통해서 사용할 수 있으며 호환성이 있는 웹 브라우저에서 인터랙티브한 3D 그래픽을 사용할 수 있도록 제공된다. <br>

> 관련 연구

**CesiumJS** : CesiumJS는 플러그인 없이 웹브라우저에서 3D 지구본과 2D 지도를 생성하기 위한 javaScript 라이브러리 이다. 하드웨어 가속 그래픽에 WebGL을 사용하며 크로스 플랫폼, 크로스 브라우저 이며 동적 데이터 시각화에 맞게 조정한다. CesiumJS가 제공하는 기능 중 3D Tiles는 데스크탑, 웹 및 모바일 애플리케이션 전반에 걸쳐 방대한 이기종 3D 지리 공간 콘텐츠를 공유, 시각화, 융합 및 상호작용하기 위한 개방형 사양이다.  <br>
**cityGML** : CityGML(City Geography Markup Language)은 인터넷 환경에서 3차원 공간정보를 표현하고 저장, 공유 할 수 있는 XML 기반 언어이자 데이터 구조 이다. 3차원 공간객체 간의 관계를 기하(geometry), 위상(topology), 의미(semantics) 및 모습(appearance) 등의 속성들로 정의하고 있으며, 3차원 공간 정보를 인터넷에 연결된 시스템끼리 쉽게 주고 받을 수 있도록 하는 국제 표준이다. 현재 CityGML 3.0이 사용되고 있으며 상세한 3차원 실내 정보 및 내외부를 구분할 수 있는 LoD(Level Of Detail) 개념이 추가 되었으며, BIM 데이터와의 통합이 가능해진 상태 이다.<br>

> 연구 방법

본 연구에서는 cityGML 데이터 셋을 생성하고, Cesium을 통해 만든 지도 위에 매핑한다. 전기차 충전소 현황을 조사한 후 해당 주소를 좌표로 변환 하고 변환 좌표와 겹치는 위치의 LoD의 색상을 변경 한다. 본 연구에서의 시각화는 다음과 같은 순서로 실행된다.

1. 국가공간정보포털 오픈마켓의 연속수치지형도를 활용하여 Qgis를 통해 3D로 변환한다.
2. glTF 포맷으로 지정함으로써 cityGML데이터 셋을 생성한다.
3. cesiumJS를 활용하여 지도를 생성한다.
4. cityGML 데이터 셋을 생성한 지도에 매핑한다.


> 참고 자료

[1] '브이월드3D지도서비스성능향상을위한3D타일적용방안연구'<br>
김태훈(Kim Tae Hoon),장한솔(Jang Han Sol),유성환(Yoo Sung Hwan),and 고준희(Go Jun Hee). "브이월드 3D 지도 서비스 성능 향상을 위한 3D 타일 적용 방안 연구." 대한공간정보학회지 25.1 (2017): 55-61. <br>
http://www.riss.kr/search/detail/DetailView.do?p_mat_type=1a0202e37d52c72d&control_no=4ec6e9f65ef9a145c85d2949c297615a&keyword=%EB%B8%8C%EC%9D%B4%EC%9B%94%EB%93%9C

[2] '브이월드서비스개선을위한사용자만족도조사및분석에관한연구'<br>
강진아,황정래,Kang Jin A,and Hwang Jung Rae. "브이월드 서비스 개선을 위한 사용자 만족도 조사 및 분석에 관한 연구." 한국공간정보학회지 22.6 (2014): 23-32.<br>
http://www.riss.kr/search/detail/DetailView.do?p_mat_type=1a0202e37d52c72d&control_no=555c2fb23b6cf4547f7a54760bb41745&keyword=%EB%B8%8C%EC%9D%B4%EC%9B%94%EB%93%9C

[3] '타일렌더링 기법을 이용한 HTML5/WebGL기반 3차원 공간데이터 렌더링 속도 개선' <br>
http://ttsn.riss.kr/view/sd;streamdocsId=72059243200081516

[4] '2018년과 이후 JavaScript의 동향 - JavaScript(ECMAScript)' <br>
https://d2.naver.com/helloworld/7495331
