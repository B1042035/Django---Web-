# Django-創建Web框架
b1042035楊舒晴 b1042036蔣淑雅 b1042044崔芸榕


* [Web框架](#web框架)
* [Django](#django)

* [使用pip在Ubuntu上安裝Django Web Framework](#ubuntu更新)
  - [ubuntu更新](#ubuntu更新)
  - [使用pip安裝](#使用pip安裝)
  - [檢查安裝與版本](#檢查安裝與版本)
  - [查看ip位址](#查看ip位址)
* [基本web框架應用](#基本web框架應用)
  - [創建新項目](#創建新項目)
  - [啟動數據庫](#啟動數據庫)
  - [創建管理用戶](#創建管理用戶)
  - [在配置中修改ALLOWED_HOSTS](#在配置中修改ALLOWED_HOSTS)
  - [啟動服務器](#啟動服務器)
  - [訪問網頁](#訪問網頁)
  - [訪問服務器管理頁面](#訪問服務器管理頁面)
* [web框架新增內容](#web框架新增內容)
  - [建立app](#建立app)
  - [創建模型](#創建模型)
  - [admin註冊](#admin註冊)
  - [在管理頁面新增內容](#在管理頁面新增內容)
* [影片網址](#影片網址)
* [參考資料](#參考資料)

## web框架
Web應用框架（Web application framework）是一種電腦軟體框架，用來支援動態網站、網路應用程式及網路服務的開發。這種框架有助於減輕網頁開發時共通性活動的工作負荷，例如許多框架提供資料庫存取介面、標準模板以及會話管理等，可提昇程式碼的可再用性。

主要分成三種類：模型 - 視圖 - 控制器（MVC（Model view controller））、內容管理系統、三部分組織模式。

## Django
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
sudo apt install python3-django
sudo pip3 install django
```

### 檢查安裝與版本
確認是否安裝成功和安裝的版本
```
django-admin --version
```

![檢查安裝與版本](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E6%AA%A2%E6%9F%A5%E5%AE%89%E8%A3%9D%E8%88%87%E7%89%88%E6%9C%AC.jpeg)


### 查看ip位址

```
ifconfig
```
先記下主機的IP位址


## 基本web框架應用

### 創建新項目
創建一個新項目（files可更改為想要的檔案名）
```
django-admin startproject files
```

運行項目
```
ls files/
```
![創建新項目](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E5%89%B5%E5%BB%BA%E6%96%B0%E9%A0%85%E7%9B%AE.jpeg)

從上面的輸出可以看到項目底下有一個 manage.py

移至剛剛新建的第一個項目
```
cd files/
```
![cd](https://github.com/B1042035/Web-framework-photo/blob/main/images/cd.jpeg)

### 啟動數據庫
```
python3 manage.py migrate
```

![啟動數據庫](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E5%95%9F%E5%8B%95%E6%95%B8%E6%93%9A%E5%BA%AB.jpeg)

代表啟動成功

### 創建管理用戶
```
python3 manage.py createsuperuser
```

![創建用戶](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E5%89%B5%E5%BB%BA%E7%94%A8%E6%88%B6.jpeg)

輸入用戶名（將其保留為空白可以維持使用ubuntu當下的用戶名稱），電子郵件和密碼

如圖 終端機會給予設定帳號密碼的提示（密碼不能太短、不能只有數字）

### 在配置中修改ALLOWED_HOSTS
```
nano ~/files/files/settings.py
```
files請更改為剛剛取的檔名

![修改IP](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E4%BF%AE%E6%94%B9IP.jpg)

我們必須修改框架配置中的指令之一，ALLOWED_HOSTS指令定義了可用於連接到框架的地址或域名白名單

請將我們主機的IP位址更改上去

### 啟動服務器
```
python3 manage.py runserver 0.0.0.0:8000
```
0.0.0.0請更改成主機IP位址

Django服務器將啟動（若要停止服務器，請按CTRL + C）

![啟動服務器](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E5%95%9F%E5%8B%95%E6%9C%8D%E5%8B%99%E5%99%A8.jpeg)

### 訪問網頁
打開瀏覽器並開啟網頁
```
0.0.0.0:8000/
```
0.0.0.0請更改成主機IP位址

![訪問網頁](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E8%A8%AA%E5%95%8F%E7%B6%B2%E9%A0%81.jpeg)

看到畫面代表框架正常工作

### 訪問服務器管理頁面
同樣開啟網頁
```
0.0.0.0:8000/admin/
```
0.0.0.0請更改成主機IP位址

![登入](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E7%99%BB%E5%85%A5.jpeg)


輸入剛剛設定的帳號密碼

![進入管理頁面](https://github.com/B1042035/Web-framework-photo/blob/main/images/%E9%80%B2%E5%85%A5%E7%AE%A1%E7%90%86%E9%A0%81%E9%9D%A2.jpeg)

成功進入web框架的管理頁面


## 影片網址
實作影片網址
[https://youtu.be/kRpCTgAxE2s](https://youtu.be/kRpCTgAxE2s)

## web框架新增內容
### 建立app
CTRL+C 關閉server頁面後，建立一個名為"Post"的App
```
./manage.py startapp post
```

到setting.py找到 INSTALLED_APPS 這個 list， 加入 "post"
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    # 加入 post
    'post'
]
```
即註冊完app

### 創建模型
同上，進入 models.py 建立一個簡單的範本，裡面只有標題跟內容
```
from django.db import models

class Post(models.Model):
    title = models.CharField('title', max_length=20)
    content = models.CharField('content', max_length=200)
```
設定title和content是一個 Character Field，用來存放文字，而 max_length 是用來設定最多幾個字

接著把資料結構創建到資料庫中
```
./manage.py makemigrations post
./manage.py migrate
```
makemigrations 會創建一些 ORM 的 SQL 指令讓等一下的 migrate執行（用來把資料結構input到資料庫中），migrate就會執行這個動作

資料庫結構就會和 model 同步

### admin註冊
修改 admins.py，將我們的 app 表單註冊到後台
```
from django.contrib import admin
from .models import Post

class PostAdmin(admin.ModelAdmin):
    list_display = ('id', 'title', 'content')
    search_fields = ('title', 'content')

admin.site.register(Post, PostAdmin)
```



## 參考資料
 [https://zh.wikipedia.org/wiki/Django](https://zh.wikipedia.org/wiki/Django)
 [https://zh.wikipedia.org/zh-tw/Web%E5%BA%94%E7%94%A8%E6%A1%86%E6%9E%B6](https://zh.wikipedia.org/zh-tw/Web%E5%BA%94%E7%94%A8%E6%A1%86%E6%9E%B6)
 [https://ubunlog.com/zh-TW/django-framework-instalacion-ubuntu/#Iniciar_la_base_de_datos](https://ubunlog.com/zh-TW/django-framework-instalacion-ubuntu/#Iniciar_la_base_de_datos)
 [https://www.chunhongweb.com/django-tutorial-ep-one/](https://www.chunhongweb.com/django-tutorial-ep-one/)
