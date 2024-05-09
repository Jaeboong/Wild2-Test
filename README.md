# Wild2 팀

**주제** : 캠퍼스 신문고

**상황** : 대학 생활을 하다가 불편 사항이 점점 눈에 하나씩 보이기 시작한다. 이에 대한 건의를 하고 싶다. 나는 캠퍼스를 개선하고자 하는 의지가 강한 학생이다.

**문제점** : 건의를 하고 싶지만 어느 부서에 건의를 해야 하고, 담당 부서를 찾기 힘들어하는 경우.
`내가 문제라고 생각하는 것이 괜히 “나만 불편한 건가?” 라는 생각이 들기도 하고 막상 건의를 하려니 부담이 되는 경우.

**방안** : 학생들로부터 공식적으로 불만 사항/요구 사항을 지속적으로 수집하여 캠퍼스를 개선하고 대학 커뮤니티의 진화하는 요구와 선호도에 맞게 발전하도록 도와주는 서비스를 마련한다.
투표와 게시판을 통해 학생들이 본인들의 생각을 자유롭게 표출하도록 하고, 학생들로부터 많은 공감을 얻은 불만 사항/요구 사항은 빠르고 적극적으로 해결하도록 도와주는 서비스를 제공한다.
중간에 캠퍼스 신문고가 개입하여, 문제를 빠르게 해결하도록 학생과 학교 측의 원활한 대화를 유도한다. (미팅플랜까지 제시)

<br><br>
 hi

### 시나리오

```
김지영은 고려대학교 세종캠퍼스의 학생으로, 캠퍼스 내에서 개선이 필요한 사항이나 불만 사항을 학교 관리자에게 알리고자 합니다.
그러기 위해 캠퍼스 신문고 서비스를 이용하려고 합니다.
```

### 기능리스트

1. 게시글 생성 (**`/api/posts/create`**)
    - **요청 방식:** POST
    - **요청 데이터:**
        - **`title`**: 게시글 제목
        - **`content`**: 게시글 내용
    - **응답 데이터:** 생성된 게시글 ID 및 성공 여부 메시지
2. 투표 (**`/api/posts/{post_id}/vote`**)
    - **요청 방식:** POST
    - **요청 데이터:**
        - **`option`**: 투표 옵션
    - **응답 데이터:** 투표 결과 및 성공 여부 메시지
3. 댓글 (**`/api/posts/{post_id}/comments`**)
    - **요청 방식:** POST
    - **요청 데이터:**
        - **`comment`**: 댓글 내용
    - **응답 데이터:** 생성된 댓글 ID 및 성공 여부 메시지
4. 내 정보 페이지 (**`/api/user/profile`**)
    - **요청 방식:** GET
    - **요청 데이터:** 없음
    - **응답 데이터:** 사용자 프로필 정보
5. 설문조사 생성 및 관리 (**`/api/surveys`**)
    - **요청 방식:** POST
    - **요청 데이터:**
        - **`question`**: 설문조사 질문
        - **`options`**: 선택 옵션 (객관식 등)
    - **응답 데이터:** 생성된 설문조사 ID 및 성공 여부 메시지
6. 분석 및 보고 (**`/api/reports`**)
    - **요청 방식:** GET
    - **요청 데이터:** 없음
    - **응답 데이터:** 신문고 내용 분석 보고서 및 시각화 결과

**추가하고 싶은 기능**
1. 마일리지 제도 : 신문고에 올린 게시글에 추천 시스템을 넣고 추천 수에 비례해 마일리지 적립
적립된 마일리지로 기프티콘이나 식권 같은 경품을 받는 시스템 추가(이 기능으로 하여금 학생들의 많은 참여 유도)
