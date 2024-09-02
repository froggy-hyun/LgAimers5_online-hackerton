# LgAimers5_online-hackerton
**LgAimers5기 온라인 해커톤 **   

<img src="/readme_img/contest_info.png" width="200" />
<img src="/readme_img/contest_info2.png" width="600" />

### <제품 이상 여부 판별 프로젝트>
![easyme](/readme_img/proj.png)

### <최종 결과>
![easyme](/readme_img/final_score.png)
![easyme](/readme_img/feature_importance.png)


#### [개요]​
최근 기계학습 모델의 발전과 함께 제품의 생산 단계에서 이상 여부를 미리 판단하려는 시도가 증가하고 있습니다. 이번 경진대회에서는 공정 과정의 여러 가지 데이터를 이용해 이상 여부를 판별하는 모델을 구현하고 그 성능을 비교하고자 합니다.

#### [데이터 셋 구성]  
센서 데이터 이번 대회에서는 각종 공정 과정에서 발생한 데이터들이 data 폴더 아래 2개의 파일로 제공됩니다.

train.csv test.csv 각 칼럼의 의미는 현업 전문가가 설명해주신 영상(LG LMS 내에 『LG 전자 VS본부 해커톤 문제 및 도메인 지식 소개』 모듈)과 일부 칼럼에 대해 주석을 달아주신 [칼럼 설명.xlsx]을 참고해 주세요. 각 칼럼의 이름은 원본 데이터 파일의 이름이 포함되어 있습니다. 칼럼 이름의 형식은 (원본칼럼이름)_(원본파일이름)입니다.

#### [학습용 데이터] 
학습용 데이터는 data/train.csv 으로 제공됩니다. 모델에 입력하는 값인 X변수는 train.csv파일 내의 칼럼 중 target 칼럼을 제외한 모든 칼럼이 해당됩니다. 예측해야 하는 대상인 Y변수는 target 이라는 칼럼으로 제품의 이상 여부를 나타냅니다. AbNormal: 제품에 각종 이상이 있다는 의미입니다. Normal: 제품이 정상이라는 의미입니다.

#### [테스트용 데이터] 
테스트용 데이터는 아래의 제출용 제품의 이상 여부를 예측하기 위한 센서 데이터들이 포함되어 있습니다. 모든 칼럼이 학습용 데이터와 동일하지만, 아래 두 가지 내용이 다릅니다. 제품의 id가 포함되어 있습니다. 이는 제출용 제품 목록의 이상 여부를 채점하기 위해 사용됩니다. target 칼럼이 비어있습니다.

#### [제출용 제품 목록] 
예측 후 제출해야 하는 제품 목록은 submission.csv으로 제공됩니다. 제출용 제품 목록 파일에는 정답이 되는 target이 없습니다. 예측을 통해 target 칼럼을 채워 넣고 제출하세요.

#### [Random state] 
베이스 라인 코드에는 일정한 성능이 나오도록 Seed에 해당하는 RANDOM_STATE 라는 변수가 있습니다. 해당 값은 기본 110으로 설정되어 있으며, 임의로 수정할 수 있습니다.

#### [결과 지표] 
경진대회의 결과 지표를 계산하기 위해서 분류(classification) 지표인 F1 Score를 활용합니다. 이번 대회에서 사용하는 데이터 셋은 AbNormal과 Normal의 개수 차이가 심한 편으로, 예측해야 하는 대상인 AbNormal을 기준으로 F1 Score를 계산합니다.

#### [채점 방법] 
채점을 위해 submission.csv 파일을 읽고 저장해야 합니다. 읽은 파일을 위의 안내의 따라 값을 채워 넣은 후에 나온 테스트 데이터를 학습된 모델에 적용합니다. 모델에서 나온 예측 결과는 아래와 같은 형태의 CSV 파일로 저장하여야 합니다. 파일 이름은 submission.csv로 해야 합니다. 초기 디렉터리에 submission.csv파일을 저장하였다면, 오른쪽 위의 제출 버튼을 클릭해 결과를 확인할 수 있습니다.

#### [데이터 칼럼] 
**DISCHARGED SPEED OF RESIN Collect Result_Dam** : Resin 토출 Speed  
**DISCHARGED TIME OF RESIN(Stage1) Collect Result_Dam** : ****Resin 토출 시간(Stage 1 : CID)  
**DISCHARGED TIME OF RESIN(Stage2) Collect Result_Dam** : ****Resin 토출 시간(Stage 2 : Seg)  
**DISCHARGED TIME OF RESIN(Stage3) Collect Result_Dam** : Resin 토출 시간(Stage 3 : Cluster)  
**Dispense Volume(Stage1) Collect Result_Dam** : Resin 토출량 (CID)  
**Dispense Volume(Stage2) Collect Result_Dam** : Resin 토출량 (Seg)  
**Dispense Volume(Stage3) Collect Result_Dam** : Resin 토출량 (Cluster)  
**HEAD NORMAL COORDINATE X AXIS(Stage1) Collect Result_Dam** : 토출좌표  
**HEAD NORMAL COORDINATE X AXIS(Stage2) Collect Result_Dam** : 토출좌표  
**HEAD NORMAL COORDINATE Z AXIS(Stage3) Collect Result_Dam** : 토출좌표  
**HEAD Standby Position X Collect Result_Dam** : 토출대기좌표  
**HEAD Standby Position Y Collect Result_Dam** : 토출대기좌표  
**HEAD Standby Position Z Collect Result_Dam** : 토출대기좌표  
**Head Clean Position X Collect Result_Dam** : 노즐클린 좌표  
**Head Clean Position Y Collect Result_Dam** : 노즐클린 좌표  
**Head Clean Position Z Collect Result_Dam** : 노즐클린 좌표  
**Head Purge Position X Collect Result_Dam** : Resin Drain 좌표  
**Head Purge Position Y Collect Result_Dam** : Resin Drain 좌표  
**Head Purge Position Z Collect Result_Dam** : Resin Drain 좌표  
**Head Zero Position X Collect Result_Dam** : Zero 좌표  
**Head Zero Position Y Collect Result_Dam** : Zero 좌표  
**Head Zero Position Z Collect Result_Dam** : Zero 좌표  
**Machine Tact time Collect Result_Dam** : DAM공정소요시간  
**PalletID Collect Result_Dam** : PalletID  
**Production Qty Collect Result_Dam** : -  
**Receip No Collect Result_Dam** : -  
**Stage1 Circle1 Distance Speed Collect Result_Dam** : CID #1 R 수치  
**Stage1 Circle2 Distance Speed Collect Result_Dam** : CID #2 R 수치  
**Stage1 Circle3 Distance Speed Collect Result_Dam** : CID #3 R 수치  
**Stage1 Circle4 Distance Speed Collect Result_Dam** : CID #4 R 수치  
**Stage1 Line1 Distance Speed Collect Result_Dam** : CID#1 토출 스피드  
**Stage1 Line2 Distance Speed Collect Result_Dam** : CID#2 토출 스피드  
**Stage1 Line3 Distance Speed Collect Result_Dam** : CID#3 토출 스피드  
**Stage1 Line4 Distance Speed Collect Result_Dam** : CID#4 토출 스피드  
**Stage2 Circle1 Distance Speed Collect Result_Dam** : Seg #1 R 수치  
**Stage2 Circle2 Distance Speed Collect Result_Dam** : Seg #2 R 수치  
**Stage2 Circle3 Distance Speed Collect Result_Dam** : Seg #3 R 수치  
**Stage2 Circle4 Distance Speed Collect Result_Dam** : Seg #4 R 수치  
**Stage2 Line1 Distance Speed Collect Result_Dam** : Seg#1 토출 스피드  
**Stage2 Line2 Distance Speed Collect Result_Dam :** Seg#2 토출 스피드  
**Stage2 Line3 Distance Speed Collect Result_Dam** : Seg#3 토출 스피드  
**Stage2 Line4 Distance Speed Collect Result_Dam** : Seg#4 토출 스피드  
**Stage3 Circle1 Distance Speed Collect Result_Dam** : Cluser #1 R 수치  
**Stage3 Circle2 Distance Speed Collect Result_Dam** : Cluser #2 R 수치  
**Stage3 Circle3 Distance Speed Collect Result_Dam** : Cluser #3 R 수치  
**Stage3 Circle4 Distance Speed Collect Result_Dam** : Cluser #4 R 수치  
**Stage3 Line1 Distance Speed Collect Result_Dam** : Clsuter#1 토출 스피드  
**Stage3 Line2 Distance Speed Collect Result_Dam** : Clsuter#2 토출 스피드  
**Stage3 Line3 Distance Speed Collect Result_Dam** : Clsuter#3 토출 스피드  
**Stage3 Line4 Distance Speed Collect Result_Dam** : Clsuter#4 토출 스피드  
**THICKNESS 1 Collect Result_Dam** : -  
**THICKNESS 2 Collect Result_Dam** : -  
**THICKNESS 3 Collect Result_Dam** : -  



1.대회 개요

[주제]

본 대회는 공장의 각종 센서 데이터를 활용하여 제품의 이상 여부를 판별하고 그 원인을 분석하는 것을 목표로 합니다. 제공되는 데이터는 각종 센서 데이터와 제품의 이상 여부를 나타내는 레이블로 구성되어 있으며, 참가자들은 주어진 데이터를 활용하여 제품의 이상 여부를 판별하는 모델을 개발해야 합니다. [온라인 해커톤(예선)]

온라인 해커톤은 제공되는 데이터를 활용하여 제품의 이상 여부를 분류하는 모델을 개발합니다. 점수는 모델의 판별 결과를 평가하여 부여되며, 평가 방식은 아래의 평가 산식(F1-score) 에 따릅니다.

2.평가 방식

[평가 산식 : F1-score]

alt text

Public score: 전체 테스트 데이터 샘플 중 사전 샘플링된 50%로 계산합니다. Private score: Public score 에 포함되지 않은 나머지 50%의 테스트 데이터로 계산합니다.

[평가 기준]

온라인 해커톤(예선)

LG Aimers 수료 조건 : Phase 1 온라인 AI 교육을 이수하고, Phase 2 온라인 해커톤의 Baseline 모델 성능 기준 Public Score 0.14816556914393225 이상의 성능 모델 제출

1차 평가 : 예선 문항 리더보드의 Private Score 100% → 최종 점수(마지막으로 제출한 답안의 점수)로 평가

2차 평가 : 오프라인 해커톤 진출을 희망하는 팀은 코드 제출 후 코드 검증 Private Score 상위 총 인원 100명의 팀은 코드 및 발표자료 PPT 필수 제출 대상 (진출을 포기하는 경우, 다음 팀에게 기회가 주어집니다.) 코드 검증을 통과한 Private 상위 100명의 팀이 오프라인 해커톤 진출 단, 오프라인 해커톤은 팀 단위로 선발(1인 팀 참여 가능)하여 총 선발 인원이 100명 이상 선발될 가능성이 있음 참고 사항 Private Score는 대회 종료 즉시 공개되며, 코드 검증을 거쳐 최종 스코어가 발표됩니다.

동점자의 경우, 시간 순으로 리더 보드에 기록된 해당 점수를 먼저 기록한 팀이 더 높은 순위로 등록됩니다.

코드 검증 시 정상적으로 실행이 불가능하거나 리더 보드의 점수가 복원이 불가능한 경우, 운영진의 판단에 따라 탈락 처리될 수 있습니다.

오프라인 해커톤에 참여하기 위해서는 이전의 Phase 1 온라인 AI 교육을 이수하고, Phase 2 온라인 해커톤의 Baseline 모델 이상의 성능을 달성하여 이수하여야 참여가 가능합니다.

팀원 중 미이수자가 포함된 경우 해당 팀원을 제외하거나 팀 전체가 진출하지 않는 것을 선택하셔야 합니다.

3.참여 규칙(개인 또는 팀)

[팀 빌딩]

*팀 빌딩 기간: 8월1일(목) ~ 8월14일(수)

모든 참가자는 개인 또는 팀을 이루어 참여할 수 있습니다. 개인 참가 방법: 팀 빌딩 없이, 자유롭게 제출 탭에서 제출 가능합니다. 팀 참가 방법:

대회 홈페이지에서 [팀 빌딩 게시판] [+글쓰기]를 통해 정해진 팀 빌딩 기간 동안 팀원을 구하는 글을 게재할 수 있습니다.
보다 원활한 팀 빌딩을 위해 본인의 포트폴리오 등 파일 업로드 할 수도 있습니다.
팀 빌딩 의사가 있는 팀원은 해당 공지에 [댓글]을 통해 팀 빌딩 의사를 밝힐 수 있습니다.
팀 빌딩이 완료되면 [팀 빌딩 신청 링크]에서 팀 빌딩을 신청할 수 있습니다. 팀 빌딩 신청을 하지 않은 팀은 계속 개인 점수로 집계됩니다.
*팀 빌딩 규정

팀의 점수는 각 팀 구성원의 제출된 점수 중 최종 점수로 책정됩니다. 코드 제출 수의 합 (대회 경과 일x일일 최대 제출 수)이상인 경우 팀 병합 불가합니다. ex.)대회 2일 차 일 때, 코드 제출 수의 합이 10회 이상(2일차 x 일 최대 제출 수 5회)일 경우 팀 병합 불가합니다. 팀 빌딩 시 각 팀원은 적어도 1회 제출 기록이 있어야 합니다. 팀 빌딩 후 해당 팀의 제출 수는 팀원 중 코드를 제일 많이 제출한 팀원 기준으로 일 제출 수가 결정되며, 팀 단위로 최초 1회 제출 기록이 있어야 리더보드에 팀 순위가 반영이 됩니다. ex.)A참가자(3회), B참가자(4회)인 상태로 팀 빌딩이 되었을 때 팀의 일 제출 횟수는 B참가자를 기준으로 4회 제출(잔여 1회)로 반영됩니다. 팀 빌딩 이후 팀 해체는 불가 함으로 신중히 팀을 구성해 주시기 바랍니다. 팀 최대 인원은 최대 5명이며, 동일 인이 개인 또는 복수 팀에 중복하여 등록이 불가 하오니 신중히 팀을 구성해 주시기 바랍니다.

[외부 데이터]

본 대회는 제공하는 데이터 이외의 외부 데이터를 사용할 수 있습니다. 단, 외부 데이터는 아래의 조건을 모두 만족하는 데이터에 한하여 사용 가능합니다. 데이터는 금전적인 대가 없이 누구나 쉽게 얻을 수 있어야 합니다. 데이터는 공개된 데이터이며, 사용에 법적 제약이 없어야 합니다. 대회가 종료된 이후에도 얻을 수 있는 데이터여야 합니다. 데이터를 사용한 이유와 사용한 데이터의 출처를 반드시 코드 파일에 기록해야 합니다. 위 조건 중 하나라도 만족하지 않는 데이터를 사용할 경우, 해당 코드는 운영진의 판단에 따라 탈락 처리될 수 있습니다.

또한, 제출 시 데이터는 함께 제출되지 않으니, 데이터를 받아오는 코드와 데이터를 받아오는 방법을 코드에 반드시 포함해야 합니다.

코드 검증 단계에서 운영진이 참가자가 사용한 외부 데이터에 접근할 수 없거나 코드를 실행 시 정상적으로 불러오지 못하게 되는 경우, 해당 코드는 운영진의 판단에 따라 탈락 처리될 수 있습니다.

[코드 제출 규칙]

제출할 코드는 개발 환경에 제공되는 스켈레톤 코드로, 일체의 코드는 해당 파일 안에 작성하여야 합니다. 모든 코드는 오류 없이 실행되어야 합니다. (라이브러리 로딩 코드 포함) 전체 프로세스를 가독성 있게 정리하고 주석을 포함하여 하나의 파일로 제출해야 합니다. 추론에 사용된 모델 파일 (pth 등) 다운로드 링크 첨부해야 합니다. 사용한 사전 학습 모델의 링크, 출처를 기재하고 해당 모델을 사용한 이유를 설명해야 합니다.

[Hand Labeling 및 데이터 증강]

Hand Labeling이란, 데이터 셋의 일부 또는 전체를 코드를 통해 판별한 값이 아닌 사람이 직접 수작업으로 값을 채워 넣는 행위를 의미합니다. Hand Labeling은 현업에서도 필요에 따라 사용되는 방법이므로, 본 대회에서는 Hand Labeling 을 금지하지 않습니다. 단, Hand Labeling 을 사용한 경우, 그 기준과 방법을 코드 및 발표 자료에 반드시 상세하게 기재해야 합니다. 이는 추후 모델을 현업에 적용하게 될 경우, 현업자들의 이해 및 재현을 원활히 할 수 있도록 하기 위함입니다. 따라서 아래와 같은 경우, 발표 평가에서 불리한 점수를 받을 수 있습니다.

제3자가 코드나 발표 자료를 통해 사용한 Hand Labeling의 기준과 방법을 이해할 수 없거나 재현할 수 없는 경우

Hand Labeling을 사용한 이유를 충분히 설명하지 않은 경우

Hand Labeling을 사용한 경우, 그 기준과 방법을 코드 및 발표 자료에 상세히 기재하지 않은 경우

모델의 성능을 향상시키기 위해 데이터 증강 기법을 사용하는 것도 자유롭게 적용할 수 있습니다. 단, 데이터 증강 역시 Hand Labeling과 동일하게 기준과 방법을 이해할 수 없고, 재현할 수 없는 경우 발표 평가에서 불리한 점수를 받을 수 있습니다.

[GPU 사용]

본 해커톤은 CPU 환경에서도 충분히 실행 가능하며, 따라서 기본 모델 환경 및 제출 환경은 CPU로 제공됩니다. [예선 문항 링크] 단, GPU 자원을 활용하고 싶은 일부 참가자를 위하여 예선 기간 동안 GPU 자원(엘리스 온디맨드)을 제공합니다. GPU 자원 사용 신청 기간은 2024.8.1 오전 9시 ~ 2024.8.9 오후 6시 까지 이며, 자세한 내용은 [온라인 해커톤 GPU 사용 참고사항]을 확인 바랍니다. 엘리스 온디맨드는 추가적으로 제공되는 개발 환경이며, 모델 제출물은 반드시 예선 문항에 제출해야합니다. 이에 대한 혼동으로 제출을 잘못할 경우에 대한 참가자의 이의 제기는 받지 않습니다.

[유의 사항]

온라인 해커톤 1일 최대 제출 횟수: 5회 사용 가능 언어: Python 모든 학습, 추론의 과정 그리고 추론의 결과물들은 정상적인 코드를 바탕으로 이루어져야 하며, 비정상적인 방법으로 얻은 제출물들은 적발 시 규칙 위반에 해당됩니다. Private 랭킹은 최종 순위가 아니며 코드 검증 이후 수상자가 결정됩니다. 자세한 내용은 상단의 평가 기준을 참고해 주시기 바랍니다.
