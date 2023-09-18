# Freeboard_CRUD-with-SpringBoot
Spring Boot + Oracle DB를 활용한 작은 웹사이트 만들기(자유게시판 Part)

자유게시판을 담당하였으며, 구현 소스와 템플릿은 freeboard 폴더 하에서 작업하였습니다.


![관계도_대댓글과댓글](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/40e908ac-c284-4ec4-a874-247fd5a5b122)
* 댓글과 대댓글의 관계도 및 테이블 구성입니다.
* 원댓글의 댓글 번호를 기준, 외부키로 두고 대댓글 데이터가 저장됩니다.

![관계도_게시글_댓글_좋아요](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/3f87f346-fb45-4665-a7c4-87d7882e3364)
* 게시글과 라이크 기능을 위한 테이블 구성입니다
* 게시글 번호를 기준으로 외부키가 구성되고, 라이크 기능의 경우 좋아요를 누른 사용자의 ID를 기준하여 좋아요 중복을 방지하고 (좋아요를 누른 적있는지 확인, 없으면 INSERT 연산, 좋아요를 취소할 때는 DELETE 연산) 
* 게시글 번호를 기준으로 COUNT 집계를 통해 해당 게시글의 좋아요 수를 도출합니다.

* 테이블들은 각각 어노테이션을 활용한 일대다, 다대일 등의 관계로 구성되어있으며 CRUD 간 Join등을 수행합니다.

![자유게시판_게시판](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/b51dd542-fdac-48c3-9784-1f6bc76bd0f4)
![자유게시판_게시판_페이징_게시글 검색UI](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/c9d02594-97c1-4ac0-87fe-80ebeeb6efe9)
![자유게시판_키워드_검색_특징](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/bb341630-5f69-49f2-8218-fb5e7f1a6a7a)
![자유게시판_마지막 페이지_버튼사라짐](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/c2071cc6-c8ce-42c6-bb29-512250509c78)
* Pageable을 사용하여 페이징을 구현하고, 키워드 검색 또한 구현하였으며. 키워드 검색에 따른 리스트 또한 페이징을 적용하였습니다
* 마지막 페이지의 경우, Thymeleaf를 활용해 버튼이 사용자에게 보이지 않도록 하였습니다.

* 자유게시판 글 작성, 수정 등 페이지의 UI 입니다.
* 작성자가 아닌 경우 게시글 또는 댓글의 수정/삭제 버튼이 보이지 않도록하고, 컨트롤러에서 비회원(로그인 하지 않았을 때)의 경우 글 작성 또는 수정으로의 페이지 이동을 막는 등
* 외부인 or 글작성자가 아닌 회원 등에 의한 무단 CRUD를 방지하여 데이터 무결성을 유지하도록 하였습니다.
![자유게시판_글작성](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/27c987a9-b49d-46a4-8cd7-f5f79329db9f)
![자유게시판_작성글상세보기](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/319393c9-2951-4683-8bea-c5a42f8de1c7)
![자유게시판_타 사용자 관점_삭제수정 버튼 사라짐](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/445df623-9a06-4742-94ad-a326f2670ccf)

![자유게시판_글수정](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/8308bc6b-97ba-4a1c-891d-8582dfe59d68)
![자유게시판_글수정(수정후)](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/2aa889d1-84bb-447f-91d6-432f0e1a223d)

![자유게시판_대댓글작성](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/95fdfb6f-6d63-4ca9-9a1c-eaaf7ae3d28a)
![자유게시판_댓글작성](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/d137e7e8-7fd8-49fb-a528-20a0a7595ec6)
![자유게시판_댓글_작성후](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/d0bd5d57-30e7-4220-8b89-fda8bdb687db)

* 이외 좋아요, 신고 기능이며
* 신고 버튼의 경우 해당 게시글의 번호, 게시판, 신고 사유 등이 관리자에게 전송됩니다
![자유게시판_좋아요 누름](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/5d6cb451-e3ce-42fc-8eba-03dc9fd1f97d)
![자유게시판_신고버튼](https://github.com/bidulgi99/Freeboard_CRUD-with-SpringBoot/assets/28780657/d74c7c58-1843-403f-87eb-7965d300e423)
