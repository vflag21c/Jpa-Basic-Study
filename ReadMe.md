## JPA

### 주의
 - **엔티티 매니저 팩토리**는 하나만 생성해서 애플리케이션 전체에서 공유
 - 엔티티 매니저는 쓰레드간에 공유X ( 사용하고 버려야 한다. )
 - JPA의 모든 데이터 변경은 트랜잭션 안에서 실행

### JPQL
 - JPA를 사용하면 엔티티 객체를 중심으로 개발
 - 검색을 할 때도 테이블이 아닌 엔티티 객체를 대상으로 검색

### 엔티티 매니저 팩토리와 엔티티 매니저
![img.png](image%2Fimg.png)

### 영속성

```java
//객체를 생성한 상태(비영속) 
Member member = new Member(); 
member.setId("member1"); 
member.setUsername("회원1");

EntityManager em = emf.createEntityManager();
em.getTransaction().begin();

//객체를 저장한 상태(영속)
em.persist(member);
```

### 영속성 컨섹스트의 이점
 - 1차 캐시
 - 동일성 보장
 - 트랜잭션을 지원하는 쓰기 지연
 - 변경 감지
 - 지연 로딩

### 쓰기 지연 저장소
![img_1.png](image%2Fimg_1.png)

### 변경 감지
![img_2.png](image%2Fimg_2.png)