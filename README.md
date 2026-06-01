# NYC Lending Platform – Java Spring Boot

A fintech-style lending platform designed to showcase backend engineering skills commonly used at companies like Bank

This project includes:
- API to submit a loan application
- API to calculate risk
- API to approve or reject applications
- SQL database integration (PostgreSQL)
- JWT-based authentication
- Logging, validations, and global exception handling

## Architecture

**Tech Stack**
- Java 21
- Spring Boot 3
- Spring Security + JWT
- Spring Data JPA
- PostgreSQL
- Maven
- Lombok
- ModelMapper

---

## Data Model

### `LoanApplication`
| Field | Type | Description |
|-------|------|-------------|
| id | Long | Identifier |
| applicantName | String | Applicant’s name |
| ssn | String | Masked SSN |
| amount | BigDecimal | Loan amount |
| termMonths | Integer | Loan term |
| status | Enum | PENDING / APPROVED / REJECTED |
| riskScore | Integer | Calculated score |
| createdAt | LocalDateTime | Creation timestamp |
| updatedAt | LocalDateTime | Update timestamp |

---

##  Endpoints

### Submit a loan application  
**POST** `/api/loans/apply`
```json
{
  "applicantName": "John Doe",
  "ssn": "123-45-6789",
  "amount": 15000,
  "termMonths": 36
}
