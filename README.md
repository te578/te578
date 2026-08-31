
Readme · MD
# Hi there, I'm te578 👋
 
バックエンドを軸に、インフラ・CI/CD まで自分で構築するエンジニアです。
現在は電力業界向けの SaaS の開発・運用に携わっています。
 
- 🏢 業務: 二要素認証・アカウントロック機能の設計実装 / 外部連携API開発 / WAF・CloudWatch によるセキュリティ運用
- 🔨 個人開発: Spring Boot + Next.js + PostgreSQL でマルチテナント型 BtoB SaaS「TaskFlow」を構築中
- ☁️ AWS Certified Solutions Architect – Associate
---
 
## 🚀 TaskFlow — マルチテナント型 BtoB SaaS
 
企業内プロジェクト管理ツール。認証基盤・マルチテナント基盤から、IaC・CI/CD パイプラインまで一気通貫で構築しています。
 
| リポジトリ | 内容 | 主な技術 |
|---|---|---|
| [portfolio-backend](https://github.com/te578/portfolio-backend) | REST API サーバー | Java 25 / Spring Boot 3.5 / PostgreSQL 16 / MyBatis / Flyway |
| [web](https://github.com/te578/web) | フロントエンド | Next.js / TypeScript |
| [infra-codex](https://github.com/te578/infra-codex) | AWS インフラ (IaC) | Terraform / ECS Fargate / RDS / ALB |
 
### 実装している主な要素
 
**マルチテナント**
URL パスベースのテナント識別と、スキーマ分離による DB ルーティング。テナント単位で Flyway マイグレーションを適用。
 
**認証基盤**
JWT（アクセストークン / リフレッシュトークン）。リフレッシュトークンは DB で管理（token_hash, family_id, expires_at, revoked_at）し、ブラウザ側は HttpOnly Cookie で保持。パスワードは BCrypt でハッシュ化。
 
**テスト**
JUnit 5 による単体テスト → Testcontainers による実 DB を用いた結合テスト → MockMvc による API テスト、という段階構成。
 
**API ドキュメント**
springdoc-openapi による OpenAPI / Swagger UI の自動生成。`@ControllerAdvice` で例外ハンドリングを統一。
 
**インフラ / CI/CD**
Terraform で VPC・サブネット・NAT Gateway・ALB・ECS・RDS・セキュリティグループを管理（tfstate は S3 バックエンド）。GitHub Actions から IAM OIDC フェデレーションでキーレス認証し、ECR / ECS へデプロイ。
 
**設計ドキュメント**
主要な技術選定（ECS Fargate の採用理由、CI/CD 基盤の選定理由など）を ADR（Nygard テンプレート）として記録しています。
 
> 現在は認証基盤・マルチテナント基盤・インフラが構築済みで、プロジェクト管理のコア機能を実装中です。
 
---
 
## 🛠 Tech Stack
 
**Language**
 
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=databricks&logoColor=white)
 
**Framework**
 
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)

 
**Database**
 
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
 
**Infrastructure / CI-CD**
 
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
 
**Certification**
 
![AWS SAA](https://img.shields.io/badge/AWS_Certified_Solutions_Architect_–_Associate-FF9900?style=flat&logo=amazonwebservices&logoColor=white)
