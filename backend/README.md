# 金融產品偏好紀錄系統 - 後端 (FPPRS Backend)

這是 **金融產品偏好紀錄系統 (Financial Product Preference Recording System)** 的後端專案，基於 Spring Boot 3 框架開發，提供 RESTful API 供前端介面使用。

## 🚀 技術棧

- **核心框架**: Spring Boot 3.5.13
- **開發語言**: Java 17
- **資料庫訪問**: Spring Data JPA
- **資料庫**: MySQL
- **核心安全**: Spring Security
- **API 文件**: SpringDoc OpenAPI (Swagger UI)
- **驗證**: Spring Boot Starter Validation
- **安全強化**: OWASP Encoder (防禦 XSS)
- **構建工具**: Gradle

## 🛠️ 環境需求

- **JDK**: 17 或以上版本
- **MySQL**: 8.0 或以上版本
- **IDE**: IntelliJ IDEA / Eclipse / VS Code (需安裝 Java 擴充套件)

## 📦 快速開始

### 1. 資料庫設定
- 在 MySQL 中建立名為 `esunbank` 的資料庫。
- 匯入位於 `src/main/resources/DB/esunbank.sql` 的 SQL 腳本進行結構初始化。
- 如有需要，請修改 `src/main/resources/application.properties` 中的資料庫帳號或密碼（預設為 root/root）。

### 2. 構建並執行
使用終端機執行以下指令：

```bash
# 賦予執行權限 (Linux/Mac)
chmod +x gradlew

# 執行專案
./gradlew bootRun
```

專案啟動後，後端服務將運行於 `http://localhost:8080`。

## 📖 API 文件

本專案集成了 Swagger，方便開發與測試：
- **Swagger UI**: [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)

## 📂 專案結構

- `controller/`: 處理 HTTP 請求的入口。
- `service/`: 實作核心業務邏輯。
- `dao/`: 與資料庫進行互動的層級。
- `entity/`: 資料庫對應的實體類別。
- `dto/`: 資料傳輸物件 (Request/Response)。
- `config/`: 系統配置（如 Security, Swagger）。

## 🛡️ 安全特性

- 使用 Spring Security 進行權限控管。
- 防止 SQL 注入（透過 JPA）。
- 防止 XSS 攻擊（使用 OWASP Encoder 加密輸出內容）。
- 實作稽核日誌 (Audit Log)，記錄重要操作動作。
