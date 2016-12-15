---
title: "Практическое руководство. Изменение пользовательских параметров в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "примеры [Visual Basic], изменение параметров пользователя"
  - "My.Settings - объект, изменение параметров пользователя"
  - "параметры пользователей"
  - "параметры пользователей, изменение в Visual Basic"
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Изменение пользовательских параметров в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Параметры пользователя можно изменить, присваивая новое значение свойству объекта параметров `My.Settings`.  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства.  Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра.  Параметр **Область** определяет, доступно ли свойство только для чтения. Свойство для параметра области определения **приложения** доступно только для чтения, а свойство для параметра области **пользователя** доступно для чтения или записи.  Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Значения параметров области пользователя можно изменять и сохранять во время выполнения, однако параметры области определения приложения доступны только для чтения и не могут быть изменены программным способом.  Можно изменить параметры области определения приложения при создании приложения с помощью **конструктора проекта** или путем изменения файла конфигурации приложения.  Дополнительные сведения см. в разделе [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
## Пример  
 В этом примере изменяется значение пользовательского параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь параметр пользователя `Nickname` типа `String`.  
  
 Приложение сохраняет параметры пользователя при завершении работы приложения.  Чтобы сохранить параметры немедленно, вызовите метод `My.Settings.Save`.  Дополнительные сведения см. в разделе [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## См. также  
 [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Практическое руководство. Чтение параметров приложения в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [Управление параметрами приложения \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)