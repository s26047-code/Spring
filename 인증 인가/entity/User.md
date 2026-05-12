```
package com.example.demo.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.NoArgsConstructor;
import lombok.Setter;

@Entity                    // 이 클래스가 DB 테이블과 연결된다는 표시
@Table(name = "users")     // DB에 "users"라는 이름의 테이블로 생성
@Getter @Setter            // Lombok: get/set 메서드 자동 생성 (코드 줄여줌)
@NoArgsConstructor         // Lombok: 빈 생성자 자동 생성 (JPA 필수)
public class User {

    @Id                                                    // 이 필드가 기본키(PK)
    @GeneratedValue(strategy = GenerationType.IDENTITY)   // 숫자 자동 증가 (1, 2, 3...)
    private Long id;

    @Column(unique = true, nullable = false)   // 중복 불가 + null 불가
    private String username;                   // 아이디

    @Column(nullable = false)   // null 불가
    private String password;    // 비밀번호 (암호화되어 저장됨)

    @Column(nullable = false)   // null 불가
    private String role;        // 권한 (예: "ROLE_USER", "ROLE_ADMIN")

    // 회원가입 시 User 객체 만들 때 사용하는 생성자
    public User(String username, String password, String role) {
        this.username = username;
        this.password = password;
        this.role = role;
    }
}
```