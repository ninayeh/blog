---
title: rails note - settinglogic 套件
tags: []
id: '571'
categories:
  - 工具
date: 2016-03-21 12:47:41
---

Settinglogic 這個套件可以幫我們用yaml文件進行一些設定。 使用上不複雜，在這邊整裡自己曾經做過的應用。
<!-- more -->
[https://github.com/settingslogic/settingslogic](https://github.com/settingslogic/settingslogic) **安裝**

gem install settingslogic

執行 bundle install 安裝最新的版本。 **基本操作** 

1.  在 rails 專案中新增一個rb檔案，名稱可以任意取，也可以放在任何地方，建議是可以放在 app/models/settings.rb，內容如下：
    
    class Settings < Settingslogic
      source "#{Rails.root}/config/application.yml"
      namespace Rails.env
    end
    
     
2.  然後可以在 config/application.yml 建立自己的設定檔案：(google,ga\_id,domain都可以依照自己的需求改變名稱)
    
    \# config/application.yml
    defaults: &defaults
      google:
       ga\_id: 'XX-00000000-0'
       domain: 'http://YOUR.DOMAIN.NAME'
    
    development:
      <<: \*defaults
      
    test:
      <<: \*defaults
    
    production:
      <<: \*defaults
    
    _補充：_建議是放在 config/application.yml，有時候我會命名成 settings.yml ，記得到第一步中建立的class中把source 改成
    
    source "#{Rails.root}/config/settings.yml"
    

**應用 1：**

1.  存放需要被隱藏的資料（帳號、密碼...），像是GA的的設定值 首先，把設定檔案加入到 .gitignore
    
    \# .gitignore
    config/settings.yml
    
2.  預設資料的取用方式，假如要在某個javascript檔案中取得ga\_id的話，首現把副檔名從.js 換成 .js.erb，然後就可以用ruby的方式取得我們要的變數。

<%= Settings.google.ga\_id %>

**應用 2：** 迴圈也可以唷！這個範例是在一個計畫(schedule)有許多步驟(step)的話，

\# config/setting.yml
defaults: &defaults
 schedule:
   step:
     - 步驟一：xxxxxx
     - 步驟二：xxxxxx
     - 步驟三：xxxxxx

我想要 controller 取得每一個步驟：

Settings.schedule.step.each\_with\_index do step, d

  #TODO
  @mission.title = step
  ...
end

  以上是我自己目前用過 settinglogic 筆記。