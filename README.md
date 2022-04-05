# WebGL-Based-Maps-Vworld-rendering-speed-Improvement
Improved and implemented rendering speed to improve WebGL map Vworld performance

> Need for Research

The Ministry of Land, Infrastructure and Transport of the Republic of Korea started the V-World open platform service in 2012 to expand the industry using national spatial information. V-World provides domestic 2D maps, aerial photo-based 3D maps, nationwide cadastral maps, official land prices, land use zoning maps, land use status, and an open API service that anyone can use easily.

According to [1], the demand for 3D maps is increasing because they can be used for simulation, navigation, and city planning. And it increases the waiting time that occurs during the conversion process, thereby degrading the performance.

 According to the online satisfaction survey of 1208 participants from December 26, 2013 to January 17, 2014 in [2], referring to Figure 1, the purpose of using V World, the use of 3D Open API service was the highest at 37%. However, 39% of the respondents said that it was difficult to use because of the slow rendering speed.
 
> Research Theory Definition

**Vworld** : Geospatial information open platform that gradually provides all publicly available geospatial information owned by the state to the public <br>
**WebGL** : Web-based graphics library. It can be used through the JavaScript programming language and is provided to use interactive 3D graphics in a compatible web browser. <br>
**bottleneck** : bottleneck. A part within a process that tends to slow down the entire process.

> Implementation plans

1. Vworld rendering speed improvements
2. Compensation for shortcomings due to improvement
3. Analysis of the results of comparison between the improved Vworld and the existing Vwolrd
4. Geospatial Information Industry Promotion Agency - Plan to participate in the **V-World Contest** for Geospatial Information Utilization Ideas
5. **Writing a paper** on improving rendering speed and implementing it

***

# WebGL 기반 지도 Vworld 렌더링 속도 개선
WebGL 기반 지도 Vworld 성능 향상을 위해 렌더링 속도 개선 및 구현

> 연구의 필요성

대한민국 국토교통부에서는 2012년부터 국가 공간정보를 활용한 산업 확대를 위해 브이월드 오픈 플랫폼의 서비스를 시작하였다. 브이월드는 국내 2D 지도, 항공사진 기반의 3D 지도, 전국 단위 지적도, 공시지가, 용도 지역지구도, 토지이용현황을 제공하며 누구든지 손쉽게 활용할 수 있는 오픈 API 서비스를 제공한다. 

[1]에 따르면 3D 지도는 시물레이션, 내비게이션, 도시계획 등에 활용이 가능하여 수요가 늘어나고 있지만 브이월드의 3D 지도는 건물 단위로 모델링이 되어있어  다수의 모델 랜더링 요청과 드로우콜이 CPU와 GPU 간의 전송 및 전환 과정에서 발생하는 대기시간을 증가하게 만들어 성능이 저하시키고있다.

 [2]의 2013년 12월 26일부터 2014년 1월 17일까지 총 1208명이 참여한 온라인 만족도 설문조사에 따르면 브이월드를 사용하는 목적인 Figure 1을 참조하면 3D Open Api 서비스  이용이 37%로 가장 높은 비율을 차지하고 있지만 39%의 설문자들이 랜더링 속도가 느려 사용하기 어렵다는 의견을 냈다.

> 연구 이론 정의

**Vworld** : 국가가 보유하고 있는 공개 가능한 모든 공간정보를 점진적으로 국민에게 제공하는 공간정보 오픈플랫폼 <br>
**WebGL** : 웹 기반의 그래픽 라이브러리. 자바스크립트 프로그래밍 언어를 통해서 사용할 수 있으며 호환성이 있는 웹 브라우저에서 인터랙티브한 3D 그래픽을 사용할 수 있도록 제공된다. <br>
**bottleneck** : 병목 현상. 전체 처리 과정을 느리게 만드는 경향이 있는 프로세스 내의 한 부분.


> 추진 계획

1. Vworld 렌더링 속도 개선
2. 개선으로 인한 단점 보완
3. 개선된 Vworld 와 기존 Vwolrd 비교 결과 분석
4. 공간정보 산업 진흥원 - 브이월드 **공모전** 공간정보 활용 아이디어 부문 참가 예정
5. 렌더링 속도 개선 및 구현에 관한 **논문 작성**

> 참고 자료

[1] '브이월드3D지도서비스성능향상을위한3D타일적용방안연구'
김태훈(Kim Tae Hoon),장한솔(Jang Han Sol),유성환(Yoo Sung Hwan),and 고준희(Go Jun Hee). "브이월드 3D 지도 서비스 성능 향상을 위한 3D 타일 적용 방안 연구." 대한공간정보학회지 25.1 (2017): 55-61.
http://www.riss.kr/search/detail/DetailView.do?p_mat_type=1a0202e37d52c72d&control_no=4ec6e9f65ef9a145c85d2949c297615a&keyword=%EB%B8%8C%EC%9D%B4%EC%9B%94%EB%93%9C

[2] '브이월드서비스개선을위한사용자만족도조사및분석에관한연구'
강진아,황정래,Kang Jin A,and Hwang Jung Rae. "브이월드 서비스 개선을 위한 사용자 만족도 조사 및 분석에 관한 연구." 한국공간정보학회지 22.6 (2014): 23-32.
http://www.riss.kr/search/detail/DetailView.do?p_mat_type=1a0202e37d52c72d&control_no=555c2fb23b6cf4547f7a54760bb41745&keyword=%EB%B8%8C%EC%9D%B4%EC%9B%94%EB%93%9C


