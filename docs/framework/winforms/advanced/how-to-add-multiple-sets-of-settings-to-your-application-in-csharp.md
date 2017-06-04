---
title: "How To: Add Multiple Sets of Settings To Your Application in C# | Microsoft Docs"
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
  - "application settings [Windows Forms], multiple sets"
  - "application settings [Windows Forms], C#"
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# How To: Add Multiple Sets of Settings To Your Application in C# #
В некоторых случаях может потребоваться иметь несколько наборов параметров для одного приложения.  Например, при разработке приложения, в котором ожидается частое изменение определенной группы параметров, эту группу стоит выделить в отдельный файл, который можно заменить, не изменяя другие параметры.  Visual Studio позволяет добавлять несколько наборов параметров в проект.  Доступ к дополнительным наборам параметров может осуществляться с помощью объекта "Properties.Settings".  
  
### Чтобы добавить дополнительный набор параметров в приложение, выполните следующие действия.  
  
1.  В меню **Проект** выберите **Добавить новый элемент**.  Откроется диалоговое окно **Добавление нового элемента**.  
  
2.  В диалоговом окне **Добавление нового элемента** выберите **Файл параметров**, введите имя для файла и нажмите кнопку **Добавить**, чтобы добавить новый файл параметров к решению.  
  
3.  В **Обозревателе решений** перетащите новый файл параметров в папку **Свойства**.  Это позволяет получить доступ к новым параметрам в коде.  
  
4.  Добавляйте и используйте параметры из этого файла, как при работе с любым другим файлом параметров.  Доступ к этой группе параметров можно получить с помощью объекта "Properties.Settings".  
  
## См. также  
 [Using Application Settings and User Settings](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)   
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)