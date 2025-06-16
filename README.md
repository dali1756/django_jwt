# 簡介
`JWT`驗證實作。

## 目錄
- [簡介](#簡介)
   - [目錄](#目錄)
   - [功能](#功能)
   - [使用](#使用)
   - [安裝](#安裝)
      - [安裝步驟](#安裝步驟)

## 功能
透過`JWT`驗證使用者登入後的身份驗證機制，當使用者登入後經過伺服器驗證成功產生一組`token`給使用者，之後使用者呼叫需要驗證的 API 時會附上 token，而伺服器會經過該簽名驗證後知道是哪位使用者登入，無需再透過資料庫查詢該使用者身份。

## 使用
使用`Postman`進行測試，設定 Headers 內容為`Content-Type: application/json`使用`POST`透過`api/token/`API產生`refresh`和`access`，就可使用所產生的`access`使用`GET`透過`api/protected/`API驗證是否成功。
驗證成功會顯示`{"message": "Hello XXX, successful authentication."}`。

### 安裝步驟
1. install poetry
```bash
$ poetry init -n
```
2. install package
```bash
$ poetry add django djangorestframework-simplejwt djangorestframework
```
3. run server
```bash
python3 manage.py runserver
```