---
title: "Формирование классов типов данных из XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Формирование классов типов данных из XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] включает новую функцию для создания классов типа данных из XML.  В этом разделе описано, как автоматически создавать типы данных для RSS\-канала библиотеки MSDN.  
  
### Получение XML\-данных из RSS\-канала библиотеки MSDN  
  
1.  В Internet Explorer перейдите на вкладку [RSS\-канал MSDN](http://go.microsoft.com/fwlink/?LinkId=225209).  
  
2.  Щелкните страницу правой кнопкой мыши и выберите команду **Просмотр исходного кода**.  
  
3.  Скопируйте текст канала, нажав клавиши **CTRL\+A**, чтобы выбрать весь текст, и **CTRL\+C**, чтобы скопировать его.  
  
### Создание типов данных  
  
1.  Откройте файл кода, в котором будет использоваться прокси.  Этот файл должен быть частью проекта [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
2.  Поместите курсор в такое место в файле, чтобы он был вне пределов описанных в файле классов.  
  
3.  Выберите **Изменить**, **Специальная вставка**, **Вставка XML в виде классов**.  
  
4.  Классы, называемые `rss`, `rssChannel`, `rssChannelImage` и `rssChannelItem`, создаются с необходимыми членами для доступа к элементам в RSS\-канале.  
  
### Использование созданных классов  
  
1.  После создания классов их можно использовать в коде так же, как и любые другие классы.  В следующем примере кода показана инициализация нового экземпляра класса `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
  
    ```