```
package com.example.demo.controller;

import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/auth") // SecurityConfig의 permitAll 경로와 일치해야 함
public class AuthController {

    @PostMapping("/signup")
    public ResponseEntity<String> signup(@RequestBody Object userDto) {
        // 테스트를 위해 Object로 받음. 실제로는 UserRequestDto 등을 사용하세요.
        return ResponseEntity.ok("회원가입 성공!");
    }
}
```