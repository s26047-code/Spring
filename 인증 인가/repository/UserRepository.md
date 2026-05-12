```
package com.example.demo.repository;

import com.example.demo.entity.User;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

// JpaRepository를 상속받으면 save, findAll, findById 등
// 기본적인 DB 조작 메서드를 자동으로 사용할 수 있음
public interface UserRepository extends JpaRepository<User, Long> {

    // username으로 유저 찾기
    // Optional = 유저가 없을 수도 있으니 null 대신 Optional로 감싸서 반환
    Optional<User> findByUsername(String username);

    // username이 이미 존재하는지 확인 (회원가입 중복체크용)
    boolean existsByUsername(String username);
}
```