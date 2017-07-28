---
title: "How To: Write User Settings at Run Time with C# | Microsoft Docs"
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
  - "application settings [Windows Forms], run time"
  - "application settings [Windows Forms], writing user settings"
  - "application settings [Windows Forms], C#"
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# How To: Write User Settings at Run Time with C# #
Параметры с областью действия приложения доступны только для чтения. Их можно изменить только во время разработки или путем изменения CONFIG\-файла между сеансами приложения.  Параметры, имеющие область действия пользователя, однако, можно записывать во время выполнения так же, как значение любого свойства.  Новое значение сохраняется в течение всего сеанса приложения.  Для сохранения изменений параметров между сеансами приложения вызовите метод Save.  
  
### Практическое руководство. Запись и сохранение пользовательских параметров во время выполнения с помощью C\#  
  
1.  Получите доступ к параметру и присвойте ему новое значение, как показано в примере ниже.  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Если необходимо сохранять изменения параметров между сеансами приложения, вызовите метод Save, как показано ниже.  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Параметры пользователя сохраняются в файле в папке, вложенной в скрытую локальную папку данных приложения.  
  
## См. также  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [How To: Read Settings at Run Time With C\#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)