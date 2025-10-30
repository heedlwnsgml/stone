graph TD
    subgraph "클라이언트 (Client)"
        A[User (Mobile App)]
    end

    subgraph "서버 (Server)"
        B[Spring Boot Application]
        B1[1. Controller (REST API)]
        B2[2. SecurityConfig (Spring Security)]
        B3[3. Service (Business Logic)]
        B4[4. Repository (JPA)]
        C[AI Recommendation Model]
        D[External APIs (Public Tourism DB)]

        B1 --> B2
        B2 --> B3
        B3 --> B4
        B3 --> C
        C --> D
    end

    subgraph "데이터베이스 (Database)"
        E[MySQL DB]
    end

    A -- "HTTPS (JSON)" --> B1
    B4 -- "JDBC" --> E
