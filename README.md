# OAuth2 Login

本專案是一個使用 Spring Boot 和 Spring Security 實現的 OAuth2 登入範例，展示如何整合 Google 的 OAuth2 驗證，實現單一登入功能。

## 功能特性

- **Google OAuth2 驗證**：使用者可以透過其 Google 帳戶登入應用程式。
- **Spring Boot**：簡化的應用程式配置和啟動。
- **Spring Security**：提供安全的驗證和授權機制。

## 系統需求

- **Java 17**
- **Gradle 7.4.2**

## 安裝與執行

1. **clone專案**：

   ```bash
   git clone https://github.com/justin7160/oauth2-login.git
   cd oauth2-login
   ```

2. **設定 Google OAuth2 憑證**：

   - 前往 [Google Cloud Console](https://console.cloud.google.com/)，創建一個新的專案。
   - 啟用 **OAuth 同意畫面**，並設定必要的資訊。
   - 在 **憑證** 頁面，創建 **OAuth 2.0 用戶端 ID**，選擇應用程式類型為 **Web 應用程式**。
   - 在 **授權重新導向 URI** 中添加 `http://localhost:8080/login/oauth2/code/google`。
   - 取得 **用戶端 ID** 和 **用戶端密鑰**。

3. **建構與執行應用程式**：

   - 使用 Gradle 建構專案：

     ```bash
     ./gradlew build
     ```

   - 執行應用程式：

     ```bash
     ./gradlew bootRun
     ```

   - 應用程式將在 `http://localhost:8080` 運行。

## 新增功能（2025-07-10）

- **Redis Session 儲存**：整合 Spring Session 與 Redis，將使用者登入 session 儲存在 Redis 中，支援多實例架構並提升 session 穩定性。  


## 使用說明

- **登入流程**：
  1. 訪問 `http://localhost:8080`，系統將自動重定向至 Google 的登入頁面。
  2. 進行 Google OAuth2.0 驗證並確認登入。
  3. 驗證完成後，將跳轉回應用程式，並顯示使用者名稱。

## 流程

第一張：從 `http://localhost:8080` 進入後導向 Google OAuth2.0 登入。
![image](https://github.com/user-attachments/assets/c72e6285-4f64-4333-9406-8f4b63438d13)

![image](https://github.com/user-attachments/assets/2a00a6e1-90ec-4fa5-aea6-3877fbf00ce3)

第二張：Google 驗證完成並確認登入。

![image](https://github.com/user-attachments/assets/d1d3fd57-5f9d-4360-9729-c6efab5c75f7)

第三張：返回專案本身，顯示使用者名稱。
![image](https://github.com/user-attachments/assets/e777894a-2ca8-40e1-a53c-ecf306a60864)




