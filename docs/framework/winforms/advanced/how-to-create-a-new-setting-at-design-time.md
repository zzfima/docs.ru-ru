---
title: "How To: Create a New Setting at Design Time | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "application settings [Windows Forms], design time"
  - "application settings [Windows Forms], creating"
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How To: Create a New Setting at Design Time
Можно создать новый параметр во время разработки с помощью конструктора параметров.  Конструктор параметров является интерфейсом в стиле сетки, который позволяет создавать новые параметры и указывать свойства для этих параметров.  Для новых параметров необходимо указать имя, значение, тип и область.  После создания параметр становится доступен в коде.  
  
### Чтобы создать новый параметр во время разработки на C\#, выполните следующие действия.  
  
1.  В **обозревателе решений** разверните узел **Свойства** проекта.  
  
2.  Дважды щелкните SETTINGS\-файл, в который требуется добавить новый параметр.  Имя этого файла по умолчанию — Settings.settings.  
  
3.  В конструкторе параметров задайте для создаваемого параметра имя, значение, тип и область.  Каждая строка представляет один параметр.  
  
### Чтобы создать новый параметр во время разработки на Visual Basic, выполните следующие действия.  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши узел проекта и выберите пункт **Свойства**.  
  
2.  На странице **Свойства** перейдите на вкладку **Параметры**.  
  
3.  В конструкторе параметров задайте для создаваемого параметра имя, значение, тип и область.  Каждая строка представляет один параметр.  
  
## См. также  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [How To: Change the Value of an Existing Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)