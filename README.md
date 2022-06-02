# Django-創建Web框架
b1042035 b1042036 b1042044


* [Web框架](#web框架)
* [Web框架](#apache)

* [使用pip在Ubuntu上安裝Django Web Framework](#ubuntu更新)
  - [ubuntu更新](#ubuntu更新)
  - [使用pip安裝](#使用pip安裝)
  - [檢查安裝與版本](#檢查安裝與版本)
  - [查看ip位址](查看ip位址)
* [基本Django應用](#基本django應用)
  - [創建新項目](創建新項目)
* [參考資料](#參考資料)

## web框架
Django 是一個由 Python 編寫的一個開放原始程式碼的 Web 應用框架。

使用 Django，只要很少的代碼，Python 的程式開發人員就可以輕鬆地完成一個正式網站所需要的大部分內容，並進一步開發出全功能的 Web 服務 Django 本身基於 MVC 模型，即 Model（模型）+ View（視圖）+ Controller（控制器）設計模式，MVC 模式使後續對程式的修改和擴展簡化，並且使程式某一部分的重複利用成為可能。

![1652793397817](https://user-images.githubusercontent.com/105623904/168819988-9acac526-bd0c-470f-ac2f-b70d7558c400.jpg)

## Apache
Apache HTTP Server（簡稱Apache）是Apache軟體基金會的一個開放原始碼的網頁伺服器軟體，可以在大多數電腦作業系統中運行。由於其跨平台和安全性，被廣泛使用，是最流行的Web伺服器軟體之一，維基百科網站的伺服器就使用了Apache。

## 使用pip在ubuntu上安裝django web framework

### ubuntu更新

```
sudo apt-get update 
sudo apt-get upgrade
sudo 
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
![apache狀態圖](https://user-images.githubusercontent.com/105623904/168845254-3f251372-32a8-47e1-9724-94f1e8fc9c4b.jpg)


### 查看ip

```
ifconfig
```

### 開啟瀏覽器並輸入IP，確認跳出APACHE預設主網頁
![apache預設主網頁](https://user-images.githubusercontent.com/105623904/168847359-1c029ff0-92fd-416a-9b21-23e9662be794.jpg)


### 修改主網頁
- 進入主網頁html檔案

```
sudo nano /var/www/html/index.html
```
- 將檔案原內容全部刪除，並放入以下內容，儲存並退出
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>主網頁測試</title>
</head>
<body>
	這是主網頁
</body>
</html>

```
![修改主網頁html檔案](https://user-images.githubusercontent.com/105623904/168848449-372a3ca9-d9ad-44ae-9c47-a310640915ce.jpg)

- 將網頁重新整理即可看到網頁內容改變

![主網頁](https://user-images.githubusercontent.com/105623904/168848754-7eea369d-a3cf-4a05-ae83-d94f4cf2d21d.jpg)


## 個人網站功能
- 進入目錄

```
cd /etc/apache2/mods-enabled
```
- 在目錄中建立軟式連結

```
sudo ln -s ../mods-available/userdir.conf
```
- 目錄中再建立另一個軟式連結

```
sudo ln -s ../mods-available/userdir.load
```
![軟式連結](https://user-images.githubusercontent.com/105623904/168849922-91ebc5ee-fea6-4920-8e10-3f61307aeec7.jpg)

- 編輯userdir.conf

```
sudo nano userdir.conf
```

- 刪除option之indexs參數，儲存離開

![刪除option1](https://user-images.githubusercontent.com/105623904/169029072-aeb6aef5-2fc2-4863-aba0-8f98f8b80abd.jpg)

![刪除option2](https://user-images.githubusercontent.com/105623904/169029092-f2bdc708-31d3-40cb-94fb-86e2084b8a00.jpg)

- 重啟apache
 ```
sudo systemctl restart apache2 
```

- 為使用者建立存放個人網頁的目錄(圈起來的地方請修改成自己的使用者名稱)
 ```
mkdir /home/b1042303/public_html
```
![個人網頁目錄](https://user-images.githubusercontent.com/105623904/169030516-0608618a-6366-49c7-bc69-a931a1db0b05.jpg)

- 為使用者創建html檔(注意路徑)
```
nano /home/b1042303/public_html/index.html
```
- html檔內容放入
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>個人網頁測試</title>
</head>
<body>
	這是個人網頁
</body>
</html>
```
![個人網頁內容](https://user-images.githubusercontent.com/105623904/169032891-1fb79176-ac0a-4fa3-8c4e-cd25891622f9.jpg)

- 開啟瀏覽器並輸入IP及使用者名稱(注意要加波浪符)，即可看到個人網頁

![1652875102872](https://user-images.githubusercontent.com/105623904/169033590-1c055d88-6d87-468c-aa74-911d4a3a5d46.jpg)


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
 [https://ithelp.ithome.com.tw/articles/10225447](https://ithelp.ithome.com.tw/articles/10225447)
 [https://zh.wikipedia.org/wiki/%E7%B6%B2%E9%A0%81%E4%BC%BA%E6%9C%8D%E5%99%A8](https://zh.wikipedia.org/wiki/%E7%B6%B2%E9%A0%81%E4%BC%BA%E6%9C%8D%E5%99%A8)
