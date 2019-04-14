1. 개발환경(프레임워크)
   - IDE : STS 3.9.7
   - Spring Boot 1.5.10
   - JAVA8
   - Gradle : 빌드 자동화
   - lombok : 코드 어노테이션 간결화
   - H2 : 내장DB

2. 문제해결 전략
   - 최대한 간결한 프로그램을 위해 Spring Boot, Gradle, lombok 을 사용
   - DB도 H2 내장DB를 사용하여 DB 연결 및 Mapper 사용안함
   - CSV파일 분석결과 주어진 포멧형태로 DB에 저장하면 필수 개발 API의 SQL문이
     길어질 것으로 판단되어, migration하여 DB저장
   - JWT는 미완성

3. 빌드 및 실행 방법 기술
   - STS 3.9.7 설치 후 workspace에 ZIP파일 압축해제
   - File > Import > Exisiting Project into Workspace 로 등록
   - Run as > Spring Boot App 로 실행 

    1) 데이터파일에서 각 레코드를 DB에 저장하는 API 실행
        - URL : /saveCSVFile
        - Method : post
        - parameter : filePath
        - parameter value : filePath+fileName

     2) 주택금융 공급 금융기관(은행) 목록 출력 API 실행
        - URL : /bankList
        - Method : get  

     3) 년도별 각 금융기관의 지원금액 합계를 출력 API 실행
        - URL : /yearBankSum
        - Method : get  

     4) 각 년도별 각 기관의 전체 지원금액 중에서 가장 큰 금액의 기관명 출력 API 실행
        - URL : /topBank
        - Method : get  

     5) 전체년도(2005-2016년)에서 외환은행의 지원금액 평균 중에서 가장 작은 금액과
       큰 금액을 출력하는 API 실행
        - URL : /kebankMinMax
        - Method : get  


테스트방법
src/test/java/api/web/test 패키지에 테스트 클래스 실행
    Debug as > JUnit Test 실행
