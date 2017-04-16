---
title: "How To: Read Settings at Run Time With C# | Microsoft Docs"
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
  - "application settings [Windows Forms], reading"
  - "application settings [Windows Forms], run time"
  - "application settings [Windows Forms], C#"
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How To: Read Settings at Run Time With C# #
Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства".  Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.  
  
### Считывание параметров во время выполнения с помощью C\#  
  
-   Доступ к соответствующему параметру через элемент Properties.Settings.Default.  В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor.  Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`.  Сведения о создании файла параметров см. в разделе [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## См. также  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [How To: Write User Settings at Run Time with C\#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)