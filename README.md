<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>청년 창업</title>
  <link href="https://cdn.jsdelivr.net/gh/webfontworld/cookierun/CookieRun.css" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      margin: 0;
      background: linear-gradient(180deg, #fffdf7 0%, #fefcf3 100%);
      background-color: #fffdf7;
      color: #333;
    }
    
.support-card {
  background-color: #f9f9f9;
  padding: 20px;
  margin-bottom: 20px;
  border-left: 6px solid #007BFF;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  border-radius: 10px;
  transition: transform 0.2s;
}
.support-card2 {
  background-color: #f9f9f9;
  padding: 20px;
  margin-bottom: 20px;
  border-left: 6px solid greenyellow;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  border-radius: 10px;
  transition: transform 0.2s;
}
.support-card3 {
  position: relative;
  background-color: #f9f9f9;
  padding: 20px;
  margin-bottom: 20px;
  border-left: 6px solid red;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  border-radius: 10px;
  transition: transform 0.2s;
}
.support-card:hover {
  transform: translateY(-3px);
}
.support-card2:hover {
  transform: translateY(-3px);
   }
.support-card3:hover {
  transform: translateY(-3px);
   }  
.toggle-btn {
  background-color: #a67c52;
  color: white;
  padding: 6px 16px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 14px;
}

.toggle-content {
  background-color: #fef7f1;
  border-left: 4px solid #a67c52;
  padding: 12px 16px;
  margin-top: 12px;
  display: none;
  border-radius: 8px;
}

.toggle-content ul {
  padding-left: 20px;
  margin: 0;
}

.toggle-content li {
  margin: 6px 0;
  font-size: 14px;
}
    /* 사이드 네비게이션 */
    .sidebar {
      width: 250px;
      background-color: #333;
      color: white;
      position: fixed;
      height: 100%;
      left: -250px;
      top: 0;
      transition: left 0.3s ease;
      padding-top: 60px;
    }
    .sidebar.open {
      left: 0;
    }
    .sidebar a {
      display: block;
      color: white;
      padding: 15px 20px;
      text-decoration: none;
      border-bottom: 1px solid #444;
    }
    .sidebar a:hover {
      background-color: #444;
    }

    /* 햄버거 버튼 */
    .hamburger {
      position: fixed;
      top: 15px;
      left: 15px;
      background-color: #333;
      color: white;
      border: none;
      padding: 10px 15px;
      cursor: pointer;
      z-index: 1000;
    }

    /* 메인 콘텐츠 */
    .main {
        flex: 1;
        margin-left: 60px; /* 햄버거 버튼 공간 확보 */
        padding: 20px;
        transition: margin-left 0.3s ease;
        width: calc(100% - 60px);
    }

    .sidebar.open ~ .main {
        margin-left: 250px;
        width: calc(100% - 250px);
    }

    @media (max-width: 768px) {
    .main {
        margin-left: 50px;
        width: calc(100% - 50px);
    }
    .sidebar {
        width: 200px;
        left: -200px;
    }
    .sidebar.open ~ .main {
        margin-left: 200px;
        width: calc(100% - 200px);
    }
}


    /* 페이지 섹션 공통 */
    .section {
      display: none;
    }
    .section.active {
      display: block;
      animation: fadeIn 0.5s;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    /* 반응형 */
    @media (max-width: 768px) {
      .sidebar {
        width: 200px;
        left: -200px;
      }
      .sidebar.open ~ .main {
        margin-left: 200px;
      }
    }
    /* 공통css */
    
    .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 22px 0px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    /*로고  css */
    .logo-img{
      height: 36px;
      object-fit: contain;
    }
    .menu {
      display: flex;
      gap: 36px;
      
      align-items: center;
    }
    .menu a {
      color: #4a3f35;
      text-decoration: none;
      font-size: 1rem;
      font-weight: 600;
      transition: color 0.2s;
    }

    .menu a:hover {
      color: #b47f55;
    }
    footer {
      text-align: center;
      padding: 24px;
      background: #f5ece3;
      font-size: 0.95rem;
      color: #6b5b50;
    }
    .section h1{
      font-family: 'CookieRun-Regular', sans-serif; 
      color: #ff7043; 
      border-left: 5px solid #ffa726;
    }
    .section h2{
      font-family: 'CookieRun-Regular', sans-serif; 
      color: #7c5c48; 
    }
    /*  홈페이지 header 파트 css */
    .had{
      padding: 60px 20px;
      text-align: center;
      background: linear-gradient(to bottom right, #fdf7f1, #fffaf0);
    }

    .had h1{
      font-size: 1.8rem;
      margin-bottom: 10px;
    }

    .had p{
      font-size: 1.1rem;
      color: #4b4b4b;
    }
    
  </style>

  <!-- 내부 JS -->
  <script>
    function toggleSidebar() {
      document.getElementById('sidebar').classList.toggle('open');
    }

    function showPage(id) {
      const sections = document.querySelectorAll('.section');
      sections.forEach(sec => sec.classList.remove('active'));
      document.getElementById(id).classList.add('active');
    }
  </script>
  <!--원활한 내부 앵커 이동을 위한 jQuery-->
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script>
  $(document).ready(function() {
    $('a[href^="#"]').on('click', function(e) {
      e.preventDefault();
      const target = $(this.getAttribute('href'));
      if (target.length) {
        $('html, body').animate({
          scrollTop: target.offset().top - 20
        }, 500);
      }
    });
  });
 //더보기-접기 toggle 
 $(document).ready(function(){
  $('.toggle-btn').click(function(){
    const content = $(this).siblings('.toggle-content');
    const btn = $(this);
    content.slideToggle(200, function(){
      btn.text(content.is(':visible') ? '접기' : '더보기');
    });
  });
});


</script>

</head>
<body>
<!-- 네비 메뉴 -->
  <nav>
    <div class="nav-container">
      <div class="logo">
        <a href = "home.html">
            <img src = "곰두리_16.png" alt = "로고" class = "logo-img">
        </a>
        </div>
      <div class="menu">
        <a href="index.html">홈</a>
        <a href="지역별 복지.html">지역별 복지</a>
        <a href="청년패스.html">k패스</a>
        <a href="#simulator">#</a>
      </div>
       
    </div>
  </nav>
  <!-- 햄버거 버튼 -->
  <button class="hamburger" onclick="toggleSidebar()">☰</button>

  <!-- 사이드 네비게이션 -->
  <nav class="sidebar" id="sidebar">
    <a href="#" onclick="showPage('gov')">정부 지원</a>
    <a href="#" onclick="showPage('academy')">청년 창업 사관학교</a>
    <a href="#" onclick="showPage('helper')">청년 창업 지원 도우미</a>
  </nav>

  <!-- 메인 콘텐츠 -->
  <header class="had">
    <h1>🚀 청년 창업에 관한 지원</h1>
    <p>창업 관련된 정보와 지원을 찾아보고 혜택을 받아보세요!</p>
  </header>
  <div class="main">
    <div id="gov" class="section active">
      <h1>&nbsp;정부 지원</h1>
      <p>청년을 위한 정부 지원 제도를 소개합니다.</p><br><hr><br>
      <p style="display: inline;">창업에 관심 있는 분이라면 한 번쯤</p><h4 style="display: inline;"> '나도 창업 지원금을 받을 수 있나?'</h4>
      <p style="display: inline;">하는 생각을 해보셨을 것 같습니다.</p>
      <p>'창업지원금'을 검색하거나 창업 포털 사이트를 찾아보면 수많은 공고를 보실 수 있는데요. 정보가 너무 많기 때문에 오히려 무엇부터 봐야 할지 막막할 수 있습니다.</>
      <p>수많은 창업 지원 사업 중 정부에서 공식적으로 운영하고, 매년 정기적으로 모집하며, 규모가 비교적 큰 대표적인 지원 사업을 정리해 보았습니다.<p><br>

    <h2 class="support-card">❗이것부터 확인하세요</h2>
            <div>
                <ul>
                    <li>정부 지원 사업은 대부분 연초(1~2월)에 모집을 시작합니다. 지금부터 나에게 해당하는 사업과 관련 준비 사항을 미리 알아보고, 공고가 뜨면 바로 신청할 수 있도록 준비해 두는 것이 좋습니다.</li>
                    <li>공식 웹사이트를 통해 기존에 선정된 사업 리스트를 살펴볼 수 있습니다. 어떤 사업이 선정되었는지 살펴보고 나에게 적용할 만한 힌트를 얻어보세요.</li>
                    <li>지원 대상, 내용, 시기는 변경될 수 있습니다. 아래 정보는 2024년 모집 공고를 기준으로 작성되었으며, 반드시 모집 시기에 해당 사업 공고의 자세한 내용을 확인하세요. *2025년 2월 20일  업데이트</li>
                </ul>
            </div><br>
     <div style="margin-bottom: 20px;">
        <h2 class="support-card">나의 경력에 맞는 지원 확인하기</h2>
            <ul>
              <li><a href="#pre" style="margin-right: 15px; font-weight: bold; color: #2c3e50; cursor: pointer;">예비 창업자</a></li>
              <li><a href="#early" style="margin-right: 15px; font-weight: bold; color: #2c3e50; cursor: pointer;">초기 창업자(3년이내)</a></li>
              <li><a href="#growth" style="font-weight: bold; color: #2c3e50; cursor: pointer;">중기 창업자(3년~7년)</a></li>
            </ul>
            </div>
    <div id="pre" class="support-card" style="margin-top: 40px;">
              <h2>💡1. 예비 창업자</h2><br>
              <button class="toggle-btn">더보기</button>
              <div class="toggle-content">
                <h3>예비창업패키지</h3><br>
                <ul>
                    <li>혁신적인 기술과 사업 모델(BM)을 보유한 예비창업자의 성공 창업을 지원하여 양질의 일자리를 창출합니다.</li>
                    <li>지원 대상: 공고일 기준 사업자 등록 및 법인 설립등기를 하지 않은 예비 창업자</li>
                    <li>지원 내용: 사업화 자금 (평균 0.5억 원), 창업프로그램 등</li>
                    <li>선정 규모: 일반분야 660명, 특화분야 120명 내외(여성 60명/소셜 벤처 60명/사내 벤처 30팀)</li>
                    <li>모집 일정: 사업 공고(2월) > 서류 평가(3월) > 인큐베이팅(4월) > 발표 평가(4월) > 선정 및 사업화 지원(4월~)</li>
                    <li>운영 기관: 창업진흥원 예비초기팀</li> 
                </ul><br>
                <h3>신사업 창업사관학교</h3><br>
                <ul>
                    <li>성장 가능성이 높은 유망 아이템으로 창업을 준비하는 예비 소상공인을 선발하여 기초 및 경영 교육, 상품화 지원, 사업화 자금 등을 지원합니다.</li>
                    <li>지원 대상: 신사업 아이디어 또는 유망 아이템으로 창업하고자 하는 예비 창업자<br>
신청 분야: 로컬크리에이터형 / 라이프스타일형</li>
                    <li>지원 내용: 사업화 자금(최대 4천만 원)</li>    
                    <li>선정 규모: 총 510명 이내 (지역별 모집 규모 상이)</li>
                    <li>모집 일정: 사업 공고(3월) > 서류, 발표 평가(4월) > 선정(4월) > 사업화 지원(4월~)</li>
                    <li>운영 기관: 소상공인시장진흥공단 창업지원실</li>
                </ul><br>
                <h3>창업중심대학 - 예비 창업자</h3><br>
                <ul>
                    <li>기준 지역별 또는 대학별 예비창업자의 우수한 기술창업 아이템, 비즈니스 모델의 사업화를 지원합니다.</li>
                    <li>지원 대상: 제시된 지역 또는 창업중심대학 기준을 충족하는 예비 창업자<br>
대학발 창업 / 지역 일반 유형으로 구분</li>
                    <li>지원 내용: 사업화자금(5천만 원 내외, 최대 1억 원), 창업 프로그램 등</li>    
                    <li>지원 규모: 총 351명 내외</li>
                    <li>모집 일정: 사업 공고(1월) > 신청·접수(1월) > 평가·발표(2월) > 사업화 지원(3월~)</li>
                    <li>운영 기관: 중소벤처기업부 창업진흥원</li>        
                </ul>
              </div>
            </div>

            <div id="early" class="support-card" style="margin-top: 40px;">
            <h2>💡2.초기 창업자(3년이내)</h2><br>
            <button class="toggle-btn">더보기</button>
            <br>
            <div class="toggle-content">
                <h3>초기창업패키지</h3><br>
                <ul>
                    <li>유망 창업 아이템 및 고급 기술을 보유한 초창기 기업에 필요한 사업화 자금을 지원합니다. (최대 1억 원)</li>
                    <li>지원 대상: 업력 3년 이내 초기 창업 기업</li>
                    <li>지원 내용: 사업화 자금 (최대 1억 원), 창업 프로그램 등</li>
                    <li>선정 규모: 총 430개사 내외</li>
                    <li>모집 일정: 사업 공고(2월) > 신청·접수(2월) > 서류평가 (3월) > 심층 인터뷰 (4월) > 발표평가 (4월) > 최종 선정 및 사업비  지원 (4월~)</li>
                </ul><br>
                <h3>창업성공패키지 청년창업사관학교 (입교생 모집)</h3><br>
                <ul>
                    <li>유망 창업 아이템 및 혁신 기술을 보유한 우수 창업자를 발굴하여 창업의 전 단계를 지원합니다.</li>
                    <li>지원 대상: 만 39세 이하, 창업 후 3년 이내 창업 기업의 대표자</li>
                    <li>지원 내용: 사업비 지원(최대 1억 원, 총사업비의 70% 이내), 창업 준비 공간 지원, 창업 교육 및 코칭, 기술 지원 등</li>
                    <li>선정 규모: 총 850명 (글로벌형 330명, 지역특화형 310명, 투자형 140명)</li>
                    <li>모집 일정: 사업 공고(1월) > 신청·접수(1~2월) > 평가·발표(2~3월) > 프로그램 진행(3월~)</li>
                    <li>운영 기관: 중소벤처기업부 중소벤처기업진흥공단 창업지원처 </li>
                </ul><br>
                <h3>창업중심대학 - 초기 창업기업</h3><br>
                <ul>
                    <li>기준 지역별 또는 대학별 초기 창업기업의 우수한 기술창업 아이템, 비즈니스 모델의 사업화를 지원합니다.</li>
                    <li>지원 대상: 제시된 지역 또는 창업중심대학 기준을 충족하는 3년 이내 창업자 (공고 상세 내용 확인)</li>
                    <li>지원 내용: 정부지원사업비(7천만 원 내외, 최대 1억 원), 창업 프로그램 등</li>
                    <li>선정 규모: 총 180개 내외 (대학발 창업 54개, 지역 일반 유형 126개)</li>
                    <li>모집 일정: 사업 공고(1월) > 신청·접수(1월) > 평가·발표(2월) > 사업비 지원(3월~)</li>
                    <li>운영 기관: 중소벤처기업부 창업진흥원</li>
                </ul>
            </div>
            </div>
            

            <div id="growth" class="support-card" style="margin-top: 40px;">
            <h2>💡3.중기 창업자(3년~7년)</h2><br>
            <button class="toggle-btn">더보기</button>
            <div class="toggle-content">
                <h3>창업도약패키지</h3><br>
                <ul>
                    <li>유망 기술창업 아이템을 보유한 도약기 창업 기업의 비즈니스 모델 혁신 및 제품‧서비스 고도화를 지원합니다.</li>
                    <li>2024년도 창업도약패키지 창업기업 모집은 ①대기업 협업형, ②일반형, ③투자병행, ④융자병행, 4가지 유형으로 분리하여 공고하며, 이 중 1개의 유형만 신청 가능합니다.</li>
                    <li>지원 대상: 창업 후 3년 초과 7년 이내 도약기 창업기업</li>
                    <li>지원 내용 및 선정 규모<br>
                        ①대기업 협업형: 사업화 자금(최대 2억 원), 창업 프로그램 / 100개사 내외<br>
                        ②일반형: 사업화 자금(최대 3억 원), 창업 프로그램 / 233개사 내외<br>
                        ③투자병행: 사업화 자금(최대 2억 원+투자 연계), 창업 프로그램 / 20개사 내외<br>
                        ④융자병행: 사업화 자금(최대 2억 원+융자 연계), 창업 프로그램 / 20개사 내외
                    </li>
                    <li>운영 기관: 중소벤처기업부 창업진흥원</li>
                </ul><br>
                <h3>창업중심대학 - 도약기 창업기업</h3><br>
                <ul>
                    <li>기준 지역별 또는 대학별 초기 창업기업의 우수한 기술창업 아이템, 비즈니스 모델의 사업화를 지원합니다.</li>
                    <li>지원 대상: 제시된 지역 또는 창업중심대학 기준을 충족하는 3년 초과 7년 이내 창업자</li>
                    <li>지원 내용: 정부지원사업비(최대 3억 원), 창업 프로그램 등</li>
                    <li>선정 규모: 총 102개 내외 (대학발 창업 유형 27개, 지역 일반 유형 75개)</li>
                    <li>모집 일정: 사업 공고(1월) > 신청·접수(1월) > 평가·발표(2월) > 사업비 지원(3월~)</li>
                    <li>운영 기관: 중소벤처기업부 창업진흥원</li>
                </ul><br>
                <h3>창업성공패키지 - 글로벌창업사관학교(입교생 모집)</h3><br>
                <ul>
                    <li>혁신 기술 및 글로벌 창업 아이템을 보유한 창업자의 성공적인 글로벌 사업화를 지원합니다.</li>
                    <li>지원 대상: 창업 7년 이내 기업 중 ① 글로벌 확장성이 높은 초격차･신산업･기후기술 분야 스타트업 또는 ➁ 글로벌 진출을 희망하는 청년창업사관학교 또는 글로벌창업사관학교 졸업기업</li>
                    <li>지원 내용: 사업화 자금 최대 1.5억 원 + 글로벌 5G 프로그램(멘토링, 해외 진출 준비, 투자 유치 등 프로그램)</li>
                    <li>선정 규모: 60명 (미국 35개사, 싱가포르 15개사, 베트남 10개사)</li>
                    <li>모집 일정: 사업 공고(1월) > 신청·접수(2월) > 평가·발표(3월) > 프로그램 진행(3월~)</li>
                    <li>운영 기관: 중소벤처기업진흥공단 창업지원처</li>
                </ul>
            </div>
            </div>
    </div>

    <div id="academy" class="section">
      <h1>&nbsp;청년 창업 사관학교</h1>
      <p>창업 교육, 멘토링, 자금 지원 등 다양한 프로그램을 운영합니다.</p>
      <a href="https://start.kosmes.or.kr/yh_mai001_001.do" target="_blank">
        &lt;청년 창업 사관학교 홈페이지 바로가기&gt;
      </a><br><br><hr><br>
      <h2 class="support-card2">청년 창업 사관학교란❓</h2><br>
      <p>중소벤처기업부의 창업성공패키지 청년창업사관학교 사업은 유망 창업아이템 및 혁신기술을 보유한 우수 창업자를 발굴하여 성공적인 창업사업화 지원을 위한 프로그램입니다.</p>
      <p>신청대상은 만 39세 이하인 자로서, 창업 후 3년 이내 창업기업의 대표자로 제한하고 있다. 사업 주관은 중소벤처기업진흥공단이 맡고 있습니다.</p><br>
      <div>
        <h2 class="support-card2">💡지원대상</h2><br>
        <h4>만 39세 이하 창업기업의 대표(창업 후 3년 이내 기업)</h4>
        <p>고용 및 부가가치 창출이 높은 기술 집약 업종(혁신 제조 융·복합 업종)</p>
      </div><br>
      <div>
        <h2 class="support-card2">💡지원 내용</h2><br>
        <ul>
            <li>💰정부지원금(기술개발 및 시제품 제작,마케팅 비용 등 지원)</li>
            <li>🏢창업인프라(창업 단계별 집중교육)</li>
            <li>📖창업교육(전담교수 1:1 집중코칭)</li>
            <li>📝창업코칭(제품개발 과정의 기술 및 장비지원)</li>
            <li>🖥️기술 지원(투자전담 운영사 활용 및 데모데이 실시 등)</li>
            <li>🎯투자 지원(투자전담 운영사 활용 및 데모데이 실시 등)</li>
            <li>🫂정책사업 연계지원(정책자금, 수출지원, 기술개발, 투자유치 연계 등)</li>    
        </ul>
      </div><br><hr>
      <br><h3 style="display: inline;">&#8251; 자세한 내용은</h3>
      <a href="https://start.kosmes.or.kr/yh_mai001_001.do" target="_blank" style="display: inline;"> 청년 창업 사관학교 홈페이지</a>
      <h3 style="display: inline;">에서 확인해보세요.</h3>
    </div>
    
    <div id="helper" class="section">
      <h1>&nbsp;청년 창업 지원 도우미</h1>
      <p>창업을 준비하는 청년을 위한 맞춤형 지원 정보를 제공합니다.</p><br><hr><br>
      <div class="support-card3">
        <h2>청년 창업 지원 도우미란❓</h2><br>
        <p>창업을 희망하거나 초기 창업 단계에 있는 청년들을 위한 다양한 지원 사업과 정보를 제공하는 역할을 합니다.</p>
        <p>이러한 지원은 자금 지원, 교육, 멘토링, 시설 이용 등 다양한 형태로 이루어지며, 청년들이 성공적으로 창업 활동을 할 수 있도록 돕습니다.</p>
      </div><br>
      <div class="support-card3">
        <h2>💡주요 지원 내용</h2>
        <button class="toggle-btn">더보기</button>
        <ul class="toggle-content">
            <li>자금 지원: 창업 자금 대출, 창업 지원금, 융자 등 초기 창업 비용을 지원합니다.</li>
            <li>교육 및 멘토링: 창업 관련 교육 프로그램, 전문가 멘토링, 비즈니스 모델 개발 등을 지원합니다.</li>
            <li>시설 및 인프라 지원: 창업 공간, 제조 장비, 연구 시설 등을 제공하여 창업 활동을 지원합니다.</li>
            <li>네트워킹 및 판로 지원: 창업 관련 행사, 전시회 참여, 대기업 연계 등을 통해 판로 개척을 지원합니다.</li>
            <li>정보 제공: 창업 관련 정책, 지원 사업, 시장 동향 등 유용한 정보를 제공합니다.</li>
        </ul>
      </div><br>
      <div class="support-card3">
        <h2>💡지원 기관 및 사이트</h2>
        <p>&#8251;&lt;클릭하면 해당 사이트로 이동합니다.&gt;</p><br>
        <button class="toggle-btn">더보기</button>
        <ul class="toggle-content">
            <li><a href="https://nbcamp.spartacodingclub.kr/" target="_blank">K-Startup</a>: 정부의 창업 지원 사업 공고 및 정보를 제공하는 대표적인 사이트입니다.</li>
            <li><a href="https://www.gov.kr/portal/orgInfo/orgmapr" target="_blank">지방자치단체</a>: 각 지역별로 청년 창업 지원 정책을 시행하고 있으며, 해당 지자체 홈페이지에서 관련 정보를 얻을 수 있습니다.</li>
            <li><a href="https://www.rg4u.co.kr/" target="_blank">창업지원센터</a>: 창업 공간, 시설, 교육 등을 제공하는 창업 지원 기관입니다.</li>
        </ul>
      </div><br>
      <div class="support-card3">
        <h2>💡창업 지원금 종류</h2>
        <button class="toggle-btn">더보기</button>
        <ul class="toggle-content">
            <li>예비/초기 창업 패키지: 창업 초기 단계에 필요한 자금과 교육, 멘토링 등을 지원합니다.</li>
            <li>청년 전용 창업 자금: 만 39세 이하의 청년 창업자 또는 예비 창업자를 위한 대출 지원 사업입니다.</li>
            <li>지역 특화 창업 지원 사업: 지역별 특성에 맞는 창업 지원 사업이 운영될 수 있습니다.</li>
        </ul>
      </div><br>
      <div class="support-card3">
        <h2>💡지원 절차</h2><br>
        <button class="toggle-btn">더보기</button>
        <ol class="toggle-content">
            <li>정보 탐색: K-Startup 또는 지방자치단체, 창업지원센터 홈페이지 등에서 지원 사업 정보를 확인합니다.</li>
            <li>상담 및 신청: 필요한 경우 창업 관련 상담을 받고, 해당 사업에 신청합니다.</li>
            <li>평가 및 선정: 신청 사업에 대한 평가를 거쳐 최종 선정 여부가 결정됩니다.</li>
            <li>지원 및 관리: 선정된 경우, 지원 사업에 따라 자금, 교육, 시설 등을 제공받고 창업 활동을 진행합니다.</li>
        </ol>
      </div><br>
      <div class="support-card3">
        <h2>💡창업 지원 도우미 활용</h2><br>
        <button class="toggle-btn">더보기</button>
        <ul class="toggle-content">
            <li>창업 관련 정보를 얻고, 필요한 지원 사업을 찾고, 신청 절차를 안내받을 수 있습니다.</li>
            <li>창업 전문가의 멘토링을 통해 사업 계획 수립 및 실행에 도움을 받을 수 있습니다.</li>
            <li>창업 관련 교육 및 네트워킹 기회를 통해 역량을 강화할 수 있습니다.</li>
        </ul>
        
      </div>
    </div>
  </div>
<footer>
    Copyright © 2025. All rights reserved.
  </footer>
<script>
    const clock = document.createElement("div");
  clock.id = "clock";
  clock.style.position = "fixed";
  clock.style.top = "24px";
  clock.style.left = "50%";
  clock.style.transform = "translateX(-50%)";
  clock.style.fontSize = "14px";
  clock.style.fontWeight = "bold";
  document.body.appendChild(clock);

  setInterval(() => {
    const now = new Date();
    clock.textContent = now.toLocaleTimeString();
  }, 1000);
</script>
</body>
</html>
