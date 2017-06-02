---
title: "How To: Change the Value of a Setting Between Application Sessions | Microsoft Docs"
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
  - "application settings [Windows Forms], changing"
  - "application settings [Windows Forms], between application sessions"
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# How To: Change the Value of a Setting Between Application Sessions
Время от времени требуется изменять значение параметра между сеансами работы приложения после его компиляции и развертывания.  Например, может потребоваться изменить строку подключения, чтобы указать правильное расположение базы данных.  Поскольку средства времени разработки недоступны после компиляции и развертывания приложения, необходимо изменить значение параметра в файле вручную.  
  
### Чтобы изменить значение параметра между сеансами работы приложения, выполните следующие действия.  
  
1.  При помощи Microsoft Notepad или другого текстового редактора или редактора XML откройте CONFIG\-файл, связанный с приложением.  
  
2.  Найдите запись для параметра, который требуется изменить.  Она должна выглядеть аналогично приведенному ниже примеру.  
  
    ```  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Введите новое значение для параметра и сохраните файл.  
  
## См. также  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)