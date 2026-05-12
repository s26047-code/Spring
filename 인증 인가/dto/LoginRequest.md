```
package com.example.demo.dto;

import lombok.Getter;
import lombok.Setter;

// 로그인 요청 시 클라이언트에서 보내는 데이터를 담는 클래스
// { "username": "홍길동", "password": "1234" } 이런 JSON을 받음
@Getter @Setter  // Lombok: get/set 메서드 자동 생성
public class LoginRequest {
    private String username;  // 아이디
    private String password;  // 비밀번호
}
```