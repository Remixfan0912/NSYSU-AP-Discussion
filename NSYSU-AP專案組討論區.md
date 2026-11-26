---
title: NSYSU-AP專案組討論區

---

[TOC]

## 前言
- 本文檔由Rix所寫，內容不保證完全正確，僅提供校務通專案組組員使用、討論
- 可前往美化後網頁版查看，模板由Gemini 4 Hydrogen生成 --> [專案組討論區網頁版](https://remixfan0912.github.io/NSYSU-AP-Discussion/)

## 討論No.1 : 安裝環境 (2026/10/1)
#### Windows安裝步驟 : 
1. 下載choco : 參考 [Chocolatey官網](https://chocolatey.org/install)
    - 以系統管理員打開PowerShell，輸入 `Get-ExecutionPolicy`
        - 如果回傳 `Restricted`，請繼續輸入下方指令
        ```
        Set-ExecutionPolicy RemoteSigned
        ```
        - 再來輸入
        ```
        Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
        ```
    - 上述執行成功後即安裝完成！輸入 `choco -v` 可以是否成功安裝。
2. 下載fvm
    - 安裝部分 : 
        - 打開cmd，輸入 `choco install fvm`
        - 安裝完成後，輸入 `fvm -v` 確認是否成功安裝
3. 下載flutter SDK
    - 安裝部分 : 
        - 打開cmd，輸入 `fvm install 3.44.8` --> 3.44.8是NSYSU-AP目前使用的版本。
        - 完成下載後輸入 `fvm list` 查看是否成功安裝
        - 由於flutter SDK已經包含Dart SDK，因此不需要再去下載Dart SDK！
    - 設定部分 : 
        - 繼續在終端機輸入 `fvm global 3.44.8`，意思是設定全域都使用flutter 3.44.8。輸入完會生成一個default資料夾，日後使用flutter指令都會連結到它。
        - **建立連結** : 先找到fvm資料夾位置，預設會在 `C:\Users\<你的User名稱>`，找到fvm點進去找到bin，複製路徑，`C:\Users\<你的User名稱>\fvm\default\bin`。
        - 打開 「編輯系統環境變數」。
        -  點「環境變數」 --> 找到PATH : 
        ![image](https://hackmd.io/_uploads/S1ajZhd9zl.png)
        - **先連點PATH**，再按新增，填入剛剛的路徑。
4. 下載Android Studio Jellyfish
    - 先到 [Android Studio歷史存檔](https://developer.android.com/studio/archive)，同意條款後，找到Jellyfish 2023.3.1 Patch 2的版本。
    - 如果顯示「找不到頁面」，要記得將語言改成英文再刷新網頁 : 
    ![螢幕擷取畫面 2026-09-29 132331](https://hackmd.io/_uploads/r1xFjpdcfl.png)
    ![image](https://hackmd.io/_uploads/S1cAjpdqGe.png)
    - 根據你的系統點擊下載。
5. 開啟Android Studio後的設定
    - 設定SDK Manager，把圖中有勾的都勾起來 : 
    ![image](https://hackmd.io/_uploads/Sy3Shpd9zl.png)

#### macOS安裝步驟 : 
1. 下載Homebrew : 參考 [Homebrew官網](https://brew.sh/)
    - 打開終端機(Terminal)，輸入下方指令
        ```bash
        /bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"
        ```
    - 上述執行成功後即安裝完成！輸入 `brew -v` 確認是否成功安裝。
2. 下載fvm
    - 安裝部分 : 
        - 打開終端機，先輸入 `brew tap leoafarias/fvm`
        - 接著輸入 `brew install fvm`
        - 安裝完成後，輸入 `fvm -v` 確認是否成功安裝
3. 下載flutter SDK
    - 安裝部分 : 
        - 打開終端機，輸入 `fvm install 3.44.8` --> 3.44.8是NSYSU-AP目前使用的版本。
        - 完成下載後輸入 `fvm list` 查看是否成功安裝
        - 由於flutter SDK已經包含Dart SDK，因此不需要再去下載Dart SDK！
    - 設定部分 : 
        - 繼續在終端機輸入 `fvm global 3.44.8`，意思是設定全域都使用flutter 3.44.8。輸入完會生成一個default資料夾，日後使用flutter指令都會連結到它。
        - **建立連結** : 先找到fvm資料夾位置，macOS預設會在 `~/fvm/default/bin`。
        - 打開終端機，輸入 `open ~/.zshrc` (若是舊版macOS請替換為 `~/.bash_profile`)。
        - 在檔案的最下方加入這行環境變數設定 : 
        ```bash
        export PATH="$HOME/fvm/default/bin:$PATH"
        ```
        - 存檔關閉後，在終端機輸入 `source ~/.zshrc` 讓設定生效。
4. 下載Android Studio Jellyfish
    - 先到 [Android Studio歷史存檔](https://developer.android.com/studio/archive)，同意條款後，找到Jellyfish 2023.3.1 Patch 2的版本。
    - 如果顯示「找不到頁面」，要記得將語言改成英文再刷新網頁 : 
    ![螢幕擷取畫面 2026-09-29 132331](https://hackmd.io/_uploads/r1xFjpdcfl.png)
    ![image](https://hackmd.io/_uploads/S1cAjpdqGe.png)
    - 根據你的Mac系統晶片（Intel 或 Apple Silicon / Mac with Apple chip）點擊對應版本下載。
5. 開啟Android Studio後的設定
    - 點選上方選單 `Android Studio` -> `Settings`，設定SDK Manager，把圖中有勾的都勾起來 : 
    ![image](https://hackmd.io/_uploads/Sy3Shpd9zl.png)
    
#### Linux安裝步驟 : 沒


## 討論No.2 : Flutter架構 & 頁面推進 (2026/11/5)
- 本次討論重點 : 
    - **一個專案的基本長相** : 
        #### 打包後要運行的平台工具包，不太會動到
        - `android/` ： 將flutter APP運行在Android上必要的工具包。
        - `ios/`： 與 `android/` 類似，包含 iOS 特定的檔案，能夠運行於Apple的平台上。
        - `web/`： 運行 Flutter App在 web 中所需的文件。
        - `Linux/、Windows/、macos/`： 針對桌面app的專案，跟ios、android工具包一個道理。
        #### 核心部分
        - `lib/`： Flutter App核心，程式在這執行。
        - `test/`： Dart 的單元測試，~~我都懶得測~~
        - `pubspec.yaml`： 其中要放入專案的依賴資源、Flutter 版本等。
    - **了解一個頁面的基本架構** : 
        - `runApp` : 將flutter app渲染到各個平台上的啟動點，放置於 `void main`（Dart程式的進入點）。
        - 何謂Widget？
        - `StatelessWidget` vs. `StatefulWidget`
        - State與StatefulWidget
        - BuildContext
    - **常見的Widget** : 
        - MaterialApp : 以Material Design Pattern為主，作為Widget Tree的根部設定
        - Scaffold : Each頁面的鷹架，flutter將其打包成底下樣式
        ![image](https://hackmd.io/_uploads/SyZFBX_Czx.png)
        - Navigator : 管理頁面結構，根據context做stack的push、pop動作




## 討論No.3 : 後端基本認識、API試打 (2026/11/12)
- 本次討論重點 : 
    - **Dio套件使用** : GET/POST、Request Body
    - **async與await** : 認識何謂非同步執行緒與使用方式
    - **iBus API試打** : JWT token、帶Authorization、取得Response
        - 先以Postman做測試，練習打API流程，建立基本Request、Response內容
        - 應用於Dio套件中，試著印出內容
    - **Parsing response raw data** : 使用jsonObject做decode、取得Map物件後解析，嘗試取值
    - **搭配ElevatedButton** : onPressed觸發打API
- 本次參考內容
    - [校務通PR - fix(bus): 遷移校車資料來源至 iBus+ API](https://github.com/nsysu-code-club/NSYSU-AP/pull/169)
- 自行查閱重點 : 
    - Generics - 泛型設計
    - JSON取值/結構
    - 非同步async執行方式

## 討論No.4 : 資料封裝與Widget呈現 (2026/11/26)
#### 連結上次討論的API
- iBus+ API資料如何呈現？
- 接續上次提問 : 
    - 何謂Generics？
    - GET/POST是甚麼？
    - JSON是甚麼？
- 思考 : 我要如何把JSON格式連結到Widget並呈現？
    - 提示 : 參考NSYSU-AP的 `...helpers/...model/...page`
#### 一個資料封裝的類別該怎麼設計？
- 過濾掉我們不需要的資料！
    - 看看postman打API給的data結構，找出自己要的資料key-value
- 透過iBus+ 回傳的公車資料，找出幾個有用的資料 : 
    - 站點名稱
    - 剩餘抵達分鐘數
    - 預計抵達確切時間
    - 每站的站牌順序
    - 公車車牌
- 為這些資料設計相對應成員
    - eg. `final int estimateMinutes` ...。
- 接著寫下建構子、設計包裝流程（傳入json取出相對應資料後傳入參數建構式）

#### 設計StatelessWidget？
- 此處開始請discuss with your friends
- 為何要設計Widget？不是有model了嗎？
    - model只是將json資料轉成dart格式，但沒有渲染效果
- 如何設計一個StatelessWidget包裝一個站點的長相？
    - 是時候展現 ~~Build~~ With AI 的設計啦~
    - 請打開你的 摳ㄉㄟˉ斯、克勞德、反重力、夸克 來實作看看吧

#### 如何把StatelessWidget放到頁面上？
- 想想為何我不把model直接渲染到頁面，而是先獨立一個StatelessWidget呢？
- 接下來請繼續打開你的AI好朋友，我們來試著把Widget放到頁面中吧！
    - 線索 : `ListView.builder`、`ListTile`
