---
title: "Практическое руководство. Сохранение пользовательских параметров в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings - объект, сохранение параметров пользователя"
  - "сохранение, сохранение параметров пользователя [Visual Basic]"
  - "параметры пользователей, сохранение"
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Практическое руководство. Сохранение пользовательских параметров в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для сохранения измененных пользовательских параметров можно использовать метод `My.Settings.Save`.  
  
 Как правило, при завершении работы приложения сохраняют измененные пользовательские параметры.  В зависимости от нескольких факторов сохранение параметров может занять несколько секунд.  
  
 Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Значения параметров области пользователя можно изменять и сохранять во время выполнения, однако параметры области определения приложения доступны только для чтения и не могут быть изменены программным способом.  Изменить параметры области приложения можно при создании приложения с помощью **конструктора проекта** или путем изменения файла конфигурации приложения.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Пример  
 В этом примере изменяется значение пользовательского параметра `LastChanged`, и эти изменения сохраняются путем вызова метода `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь пользовательский параметр `LastChanged` типа `Date`.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)