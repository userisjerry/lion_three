# lion_three
#### 24.10.10 - 10.16 // 17일 발표



## 1. 프로젝트 주제
    - 대기 오염이 높은 지역에서는 호흡기 질환 발생률이 높을 것이다.
    
## 2. 프로젝트 목표
    - 미세먼지 데이터와 호흡기 질환 데이터를 통해 상관성을 분석하고 호흡기 질환률을 낮추는 방안 탐색

  1. 문제 정의
    - 2019년~2021년 대기오염과 2019년~2021년 호흡기 질환 발생률 간 어떤 상관관계가 있는가?
    - 성별, 지역, 기간 별로 어떤 영향을 받는가?

  1. 주요 이해관계자
    1. 서울특별시, 보건 복지부 등 의료 관련 정부기관
    2. 대학병원
    3. 관련 기업들 (ex. 마스크 회사, 공기청정기 회사, 천식 호흡기 제조 회사)

  1. 분석에 사용될 데이터 셋
    - 미세먼지 데이터
        
          [106_DT_106N_03_0200076_20241010173034.csv](https://prod-files-secure.s3.us-west-2.amazonaws.com/4f7f6682-be6f-4828-a7f4-90f8fcbaf16d/de1b94a2-1b87-4fd1-a9ca-bcdb994904b8/106_DT_106N_03_0200076_20241010173034.csv)
        
    - 비염 데이터
        
        [국민건강보험공단_환경성질환(비염) 의료이용정보_20231231 (1).csv](https://prod-files-secure.s3.us-west-2.amazonaws.com/4f7f6682-be6f-4828-a7f4-90f8fcbaf16d/635ca5aa-d265-4b44-a31a-74b869eb019a/%EA%B5%AD%EB%AF%BC%EA%B1%B4%EA%B0%95%EB%B3%B4%ED%97%98%EA%B3%B5%EB%8B%A8_%ED%99%98%EA%B2%BD%EC%84%B1%EC%A7%88%ED%99%98(%EB%B9%84%EC%97%BC)_%EC%9D%98%EB%A3%8C%EC%9D%B4%EC%9A%A9%EC%A0%95%EB%B3%B4_20231231_(1).csv)
        
    - 천식 데이터
        
        [국민건강보험공단_환경성질환(천식) 의료이용정보_20231231.csv](https://prod-files-secure.s3.us-west-2.amazonaws.com/4f7f6682-be6f-4828-a7f4-90f8fcbaf16d/b79058df-c05a-4f21-9f68-a898164a3743/%EA%B5%AD%EB%AF%BC%EA%B1%B4%EA%B0%95%EB%B3%B4%ED%97%98%EA%B3%B5%EB%8B%A8_%ED%99%98%EA%B2%BD%EC%84%B1%EC%A7%88%ED%99%98(%EC%B2%9C%EC%8B%9D)_%EC%9D%98%EB%A3%8C%EC%9D%B4%EC%9A%A9%EC%A0%95%EB%B3%B4_20231231.csv)
        
   - 주요 사용 변수
        
       기간, 미세먼지 농도, 지역구, 성별, 호흡기 질환 발생 건수
        
   - Tool
        
       Google Colab, Tableau
        

## 3. 데이터 전처리
    - 미세먼지 데이터
        - 데이터에서 필요한 부분만 추출 (지역, 미세먼지, 날씨)
        - 서울시 지역구만 추출
        - 데이터 2열 (항목), 마지막 열 (Unnamed:39) 제거
        - 결측치 확인 및 평균값으로 대체
        - 지역구를 기준으로 월별 데이터를 길게 (long-form) 변환
        
    - 비염 데이터
        - date time 형식으로 변환
        - 주소  코드를 주소 명으로 변경하기 위한 데이터 프레임 생성
        - 2019-01-01 ~ 2021-12 기간에 해당하는 데이터 추출
        - 서울의 주소 코드 시작 자리가  ‘1’  이므로 ‘1’ 로 시작하는 데이터만 남기기
        - mapping 활용하여 주소 코드를  주소 명으로 변경

## 4. 대시보드 구성 및 설계
    - 도시별, 월별 미세먼지 수치 평균을 통해 도시별 평균 오염도를 확인하고 시각화를 통해 오염도가 어떻게 변화했는지 확인
    - 대기 오염도와 호흡기 질환 유병률 간의 상관관계를 시각화를 통해 분석하여 가설 검정

## 5. 타임라인 및 팀원간 역할 분담
    - 타임라인
        
        10/10 (목): 분석 주제 선정 및 역할분담
        
        10/11 (금): 코드 작성 (도식화)
        
        10/12 (토) ~ 10/13 (일): 각자 Colab 사본 만들어서 분석해보고, 작성한 코드 공부해보기
        
        10/14 (월): Tableau 대시보드, PPT 구성안 계획
        
    - 팀원 역할분담
        
        김정현: 코드 작성
        
        김진모: 코드 작성
        
        박현철: 대시보드 구성 및 설계
        
        신유리: 코드 작성, 서론(주제 선정 배경, 데이터 소개), PPT 만들기
        
        이아영: 대시보드 구성 및 설계
