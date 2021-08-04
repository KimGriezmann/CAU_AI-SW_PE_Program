# DeepLearning_BeTheLegend

## 2021. 06. 30
### To do List
1. 스탯티즈에서 타자 데이터 수집

스탯티즈(http://www.statiz.co.kr/main.php)

구단 별 타석 수 내림차순 정렬 후 9명 선수를 대상으로
선수정보 - 각타자 - Playlog - 개막부터 6/30 까지 데이터 수집

## 2021. 07. 03
### To-do List
1. 투수 유형
2. 선수 날짜별 데이터 90명 다시 복사 붙여넣기 (선수정보 - 날짜별 수집 > 선수명 기입)
3. 현재까지 모은 데이터 날짜로 묶어야하고
4. 2번에서 모은 데이터로 최근 5, 10경기 타율 뽑아야하고
5. 타율은 2번 데이터에서 활용

## 2021. 07. 05
### To-do List
1. 최근 5일 타율 계산 시, 최근 5일 내에 타수가 있으면 (=타수의 합이 0이 아니면) 그 결과를 반영
2. 최근 5일 / 최근 10일 타율 피쳐를 동시 사용시, 10일 타율에서 5일의 공백이 발생 
최근 5,10경기 타율 및 팀 별 타율 계산 완료

해야할 것: 최근 5일에 대한 타율 및 투수 유형 별 타율, 선발 투수 

※모델 개선 시에는 날짜 별로 가중치를 다르게 줄 수 있을까?

**2021.07.11 수정사항
최근 5일(변경 가능) 경기의 타율 구하기.ipynb 의 결과 테이블의
이름(recent_5days_hitter), 날짜(recent_5days_day)의 복합키로 기본키 가능, 다른 테이블과 조인할때 참고


## 2021. 07. 11
### To-do List
1. 새로운 컬럼 추가: 투수 유형별 타율, 구장별 타율, 상대 팀 타율 수정 및 한 팀 추출
2. EDA  
3. 난관 : 데이터프레임 merge시, 더블헤더 날의 중복된 merge 발생

## 2021. 07. 15
### Done List
더블헤더 코드 추가 (기본 0/ 더블헤더 1차전 1/2) > 최근 타율, 상대 타율 구하는 함수 수정


merge error 해결 : final data's length is 5296

### To-do List
stadium & pitcher type 컬럼 추가


learn MLP model


EDA visulization


※시즌 초반 경기는 어느정도 기준을  제외해야할까?

## 2021. 07. 16
### To-do List
2019/2020년 날짜별 데이터 추가 수집
(각 팀당 9명씩 총, 90명의 타자에 관한 데이터)

## 2021. 07. 23
### Done List
헤더, vs_avg, recent 5 games avg

### To-do List
1. ~recent5 / recent10~
2. ~최근 10경기 성공률 구하기~
3. ~day ex) 5월 5일 > 20200505~
4. ~day가 바뀌니까 최근 5경기 구하는 함수 수정~

5. ~vs + 날짜로 정렬해서 상대별 누적 타수, 누적 안타 구하기~
6. ~이 데이터를 사용해서 vs 타율 쓰기~
7. ~vs (두산 / @두산) 이용해서 vs팀, home/away~
8. ~hit 이용해서 result 구하기 (성공 1 / 실패 0)~


# 칼럼명 표준 정하기
1. 의미 : 표준명
2. 이름 : name
3. 날짜 : day
4. 상대(@포함) : vs
5. 상대 : vs_team
6. 결과 : result
7. 타순 : bat_order
8. 포지션 : position
9. 선발여부 : start_member
10. 타수 : ab
11. 득점 : score
12. 안타 : hit
13. 2루타 : 2_hit
14. 3루타 : 3_hit
15. 홈런 : homerun
16. 루타 : tb (total base)
17. 타점 : rbi
18. 도루 성공 : sb (stolen base)
19. 도루 실패 : cs (caught stealing)
20. 볼넷 : bb
21. 사구 : hpp (hit by pitch)
22. 고4 : ibb (intentional ball)
23. 삼진 : so (strike out)
24. 병살 : gdp (ground into double play)
25. 희타 : sh (sacrifice hit)
26. 희비 : sf (sacrifice fly)
27. 타율 : avg
28. 출루율 : obp
29. 장타율 : slg
30. OPS : ops
31. 투구 : pitch
32. avLI : avLI
33. RE24 : RE24
34. WPA : WPA
35. 상대 누적 타수 : vs_ab
36. 상대 누적 안타 : vs_hit
37. 상대 타율 : vs_avg
38. 홈/원정 : home/away
39. 홈 타율 : home_avg
40. 원정 타율 : away_avg
41. 최근 5일 타율 : recent_5days_avg
42. 최근 10일 타율 : recent_10days_avg
43. 최근 5경기 타율 : recent_5games_avg
44. 최근 10일  성공률 : success_10days
45. 최근 10경기 성공률 : success_10games
46. 더블헤더 : double
47. 팀 이름 : Team

** Team List
  
Team_2016 = ['NC','kt','LG','두산','히어로즈','KIA','롯데','삼성','SK','한화']

Team_2017 = ['NC','kt','LG','두산','히어로즈','KIA','롯데','삼성','SK','한화']

Team_2018 = ['NC','kt','LG','두산','히어로즈','KIA','롯데','삼성','SK','한화']

Team_2019 = ['NC','kt','LG','두산','키움','KIA','롯데','삼성','SK','한화']

Team_2020 = ['NC','kt','LG','두산','키움','KIA','롯데','삼성','SK','한화']

Team_2021 = ['kt','삼성','LG','SSG','NC','키움','두산','롯데','KIA','한화']


## 2021. 07. 29
### To do list
1. ~데이터 전체 merge~
2. 시즌 초반 데이터 걸러내기
3. ~사용할 데이터 : 18-21년 시즌 합친 데이터~
4. 피쳐 사용 시 근거 제시 (도메인적 접근)
5. MLP 모델 적용하기
6. test set accuracy aim : 90%
7. MLP를 보완할 모델 찾기\
~※start_member가 FALSE인 데이터에 대한 처리 필요!~
