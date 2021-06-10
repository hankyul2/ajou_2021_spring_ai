# [2021 Spring Class] Ajou AI by JBR
1. **대회목표**: 
   
   팀별로 Test data의 class를 찾는 인공지능 만들기
   
   주어진 train data와 train label을 이용하여 인공지능을 만들고 test data의 class label을 github에 제출

2. **세부 프로토콜**

   원본데이터셋: CUB200 datasets

   실습데이터셋: https://drive.google.com/drive/folders/1ItDbPIEkkQ2P2OvB1xg728tNB1NvCXkA?usp=sharing
   
   네트워크 파라미터: 제한없음

   아키텍쳐: 제한없음

   학습알고리즘: 제한없음

   딥러닝 프레임워크: PyTorch, TensorFlow 권장, 다른 프레임워크도 사용 가능

3. **순위산정:** 이미지 데이터셋의 Top-1 Accuracy

4. **팀 구성**: 사전 5인으로 구성된 팀

5. **제출데이터**: test data별 class label을 예측한 확률값. #test data의 숫자 X #class label(50개)의 확률

6. **대회진행**

   |     날짜      |      일정       |
   | :-----------: | :-------------: |
   |     시작      | 2021년 3월 24일 |
   |     중간      | 2021년 5월 21일 |
   |     기말      | 2021년 6월 11일 |
   | 최종결과 발표 | 2021년 6월 11일 |

7. **최종 결과 산출 방법:** 중간, 기말 시점의 정확도를 일정 비율로 합쳐서 최종 결과에 반영


## 퍼블릭 랭킹

  
최종 점수 집계(2021-06-11 03:31:11.031416+09:00): Total Score가 최종 업데이트 되었습니다.  
**최종 랭킹 1위는 team1 입니다. 평균 accuracy는 77.7% 입니다.**
|Ranking|Name|Penalty|Accuracy(%)|Last Submission|Total Submission Count|Total Score(%)|
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|1|team1|0|96.2|2021-06-10 22:12:57.060731+09:00|26|69.05|
|2|team8|0|95.8|2021-06-11 00:36:16.001255+09:00|48|68.8|
|3|team2|0|94.8|2021-06-10 23:44:48.014868+09:00|41|68.01|
|4|team4|0|94.6|2021-06-10 10:05:17.367921+09:00|24|68.59|
|5|team10|0|92.8|2021-06-11 03:24:57.378948+09:00|46|66.55|
|6|team12|0|91.8|2021-06-11 02:00:22.615105+09:00|22|65.88|
|7|team3|0|91.4|2021-06-10 20:31:31.431244+09:00|32|65.51|
|8|team11|0|88.6|2021-06-11 02:17:52.542471+09:00|50|63.58|
|9|team7|0|84.2|2021-06-10 23:19:11.069961+09:00|17|60.59|
|10|team9|0|83.8|2021-06-11 03:31:11.031416+09:00|23|60.31|
|11|team13(auditor)|0|80.0|2021-06-09 15:29:42.390173+09:00|5|57.59|
|12|team5|0|71.6|2021-06-10 23:58:23.589359+09:00|16|51.74|
|13|team6|0|20.8|2021-06-11 01:03:58.131489+09:00|4|16.06|
|14|professor|0|1.4|2021-05-29 10:11:56.431070+09:00|1|2.0|


**정확도는 소숫점 5자리 까지 출력됩니다.**
**Time zone is seoul,korea (UTC+9:00)**
## 퍼블릭 랭킹 제출 방법

팀별로 구성한 모델의 테스트 데이터 셋을 예측한 결과값을 `Encrypt.py` 를 이용해 암호화하여 `submission` 폴더의 해당 팀 폴더에 제출합니다.

**주의사항** : 

1. 제출 파일명은 자유롭게 작성 할 수 있습니다.(단, 폴더당 하나의 파일만 존재해야 합니다. 그렇지 않을 경우 채점이 되지 않습니다.)
2. `.github` 폴더는 건들지 않도록 합니다.
3. 하루 5회 까지 제출할 수 있고 이 이상 제출해도 채점 되지 않습니다.

Example) Team1인 경우 제출 방법

1. 예측 파일 만들기. 다음과 같은 예측 파일이 있다고 가정합니다. (query 데이터에 대한 예측 결과 파일)

   `ans.txt` 예시

   ```tex
   9
   8
   10
   99
   98
   70
   18
   33
   ```
   
2. 예측 파일(`ans.txt`)과 전달받은 키를 `Encrypt` 폴더에 넣고 `Encrypt.py`를 실행 시켜서 암호화한 예측 파일(`ans.json`)을 생성합니다. 
   생성한 파일을 (`submission/team1`)에 넣고 commit 후 push 를 실행하면 완료됩니다.

   ```python
   # 1.이메일을 통해서 전달 받은 키 파일의 경로 입력
   key_path = "key.pem"
   # 2. 예측한 결과를 텍스트 파일로 저장했을 경우 리스트로 다시 불러오기
   # 본인이 원하는 방식으로 리스트 형태로 예측 값을 불러오기만 하면 됨(순서를 지킬것)
   raw_ans_path = "ans.txt"
   ans = read_txt(raw_ans_path)
   # 3. 암호화된 파일을 저장할 위치
   encrypt_ans_path = "../submission/team1/ans.json"
   # 4. 암호화!(pycrytodome 설치)
   encrypt_data(key_path, ans, encrypt_ans_path)
   ```

이 때 꼭 로컬에서 이 스크립트를 실행해서 제출하지 않고 코랩에서 pycryptodomex 라이브러리를 설치한 후 스크립트 실행시켜서 정답 파일 만든 뒤에 제출해도 무방합니다.



## 퍼블릭 랭킹 평가 방법

query 데이터에 대한 예측값의 정확도가 퍼블릭 랭킹에 그대로 반영됩니다.

ex) `ans.txt`=(query 데이터에 대한 예측값), top 1 acc = 98%

```tex
9
8
10
99
98
70
18
33
```



## 암호화 모듈 설치 방법

설치 방법 설명은 [공식 문서](https://pycryptodome.readthedocs.io/en/latest/src/installation.html#windows-from-sources-python-3-5-and-newer)에 잘 나와있습니다. 아래 내용은 공식 문서에서 나온 내용을 가져왔습니다. 

파이썬 3.5 이상, 윈도우에서 Pycryptodomex 설치하는 방법

1. **[Once only, C Compiler가 미설치 되어있는 경우에만]** Download [Build Tools for Visual Studio 2019](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019). In the installer, select the *C++ build tools*, the *Windows 10 SDK*, and the latest version of *MSVC v142 x64/x86 build tools*.

2. Compile and install PyCryptodome:

   ```
   > pip install pycryptodomex --no-binary :all:
   ```

3. To make sure everything work fine, run the test suite:

   ```
   > python -m Cryptodome.SelfTest
   ```



문의사항이 있으신 분은 kimsungeun@ajou.ac.kr 로 문의주시길 바랍니다.
