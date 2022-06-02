# Django-創建Web框架
b1042035 b1042036 b1042044


* [Web框架](#web框架)
* [Django](#apache)

* [使用pip在Ubuntu上安裝Django Web Framework](#ubuntu更新)
  - [ubuntu更新](#ubuntu更新)
  - [使用pip安裝](#使用pip安裝)
  - [檢查安裝與版本](#檢查安裝與版本)
  - [查看ip位址](查看ip位址)
* [基本Django應用](#基本django應用)
  - [創建新項目](創建新項目)
* [參考資料](#參考資料)

## web框架
Web應用框架（Web application framework）是一種電腦軟體框架，用來支援動態網站、網路應用程式及網路服務的開發。這種框架有助於減輕網頁開發時共通性活動的工作負荷，例如許多框架提供資料庫存取介面、標準模板以及會話管理等，可提昇程式碼的可再用性。

主要分成三種類
 。模型 - 視圖 - 控制器（MVC（Model view controller））
 。內容管理系統
 。三部分組織模式

## Apache
Django 是一個由 Python 編寫的一個開放原始程式碼的 Web 應用框架。
Django的主要目標是簡化資料庫驅動的網站的開發。Django 注重組件的重用性和「可插拔性」，敏捷開發和DRY法則（Don't Repeat Yourself）。在Django中普遍使用的語言是Python，甚至包括設定檔和資料模型。

使用 Django，只要很少的代碼，Python 的程式開發人員就可以輕鬆地完成一個正式網站所需要的大部分內容，並進一步開發出全功能的 Web 服務 Django 本身基於 MVC 模型，即 Model（模型）+ View（視圖）+ Controller（控制器）設計模式，MVC 模式使後續對程式的修改和擴展簡化，並且使程式某一部分的重複利用成為可能。

## 使用pip在ubuntu上安裝django web framework

### ubuntu更新

```
sudo apt-get update 
sudo apt-get upgrade
sudo apt install net-tools
```

### 使用pip安裝
使用Python 3安裝Django

```
sudo pip3 install django
```

### 檢查安裝與版本
確認是否安裝成功和安裝的版本
```
django-admin --version
```



### 查看ip

```
ifconfig
```


## 基本django應用

### 創建新項目
創建一個新項目（files可更改為想要的檔案名）
```
django-admin startproject files
```
運行項目
```
ls files/
```
從上面的輸出可以看到項目底下有一個 manage.py

移至剛剛新建的第一個項目
```
cd files/
```

### 啟動數據庫
```
python3 manage.py migrate
```
圖片
代表啟動成功

### 創建管理用戶
```
python3 manage.py createsuperuser
```
圖片
輸入用戶名（將其保留為空白可以維持使用ubuntu當下的用戶名稱），電子郵件和密碼（密碼不能只有數字）

### 在配置中修改ALLOWED_HOSTS
```
nano ~/entreunosycero/entreunosyceros/settings.py
```
圖片
我們必須修改框架配置中的指令之一，ALLOWED_HOSTS指令定義了可用於連接到框架的地址或域名白名單。將我們主機的IP位址更改上去

### 啟動服務器
```
python3 manage.py runserver 0.0.0.0:8000
```
0.0.0.0請更改成主機IP位址
Django服務器將啟動（若要停止服務器，請按CTRL + C）

### 訪問網頁
打開瀏覽器並開啟網頁
```
0.0.0.0:8000
```
0.0.0.0請更改成主機IP位址
圖片
看到畫面代表框架正常工作

### 訪問服務器管理頁面
同樣開啟網頁
```
0.0.0.0:8000/admin
```
0.0.0.0請更改成主機IP位址

圖片

輸入剛剛設定的帳號密碼
圖片
成功進入web框架的管理頁面



## 參考資料
 [https://zh.wikipedia.org/wiki/Django](https://zh.wikipedia.org/wiki/Django)
 [https://zh.wikipedia.org/zh-tw/Web%E5%BA%94%E7%94%A8%E6%A1%86%E6%9E%B6](https://zh.wikipedia.org/zh-tw/Web%E5%BA%94%E7%94%A8%E6%A1%86%E6%9E%B6)
 [https://ubunlog.com/zh-TW/django-framework-instalacion-ubuntu/#Iniciar_la_base_de_datos](https://ubunlog.com/zh-TW/django-framework-instalacion-ubuntu/#Iniciar_la_base_de_datos)
