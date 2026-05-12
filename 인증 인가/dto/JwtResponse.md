```
package com.example.demo.dto;

import lombok.AllArgsConstructor;
import lombok.Getter;

// 로그인 성공 시 클라이언트에게 돌려주는 데이터를 담는 클래스
// { "token": "eyJhbGci...", "username": "홍길동" } 이런 JSON을 반환
@Getter
@AllArgsConstructor  // Lombok: 모든 필드를 받는 생성자 자동 생성
public class JwtResponse {
    private String token;     // 발급된 JWT 토큰
    private String username;  // 로그인한 유저 아이디
}
```