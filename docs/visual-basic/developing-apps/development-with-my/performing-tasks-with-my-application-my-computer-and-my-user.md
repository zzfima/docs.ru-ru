---
title: "Выполнение задач с My.Application, My.Computer и My.User (Visual Basic) | Microsoft Docs"
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
  - "My.Application - объект, разработка приложений"
  - "My.Computer - объект, разработка приложений"
  - "My.User - объект, разработка приложений"
  - "быстрая разработка приложений (RAD), My.Application"
  - "быстрая разработка приложений (RAD), My.Computer"
  - "быстрая разработка приложений (RAD), My.User"
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Три центральных объекта `My`, которые предоставляют доступ к информации и часто используемым функциям, это `My.Application` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>\), `My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\) и `My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\).  Эти объекты можно использовать для доступа к информации, которая связана с текущим приложением, с компьютером, на котором установлено приложение, или с текущим пользователем приложения соответственно.  
  
## My.Application, My.Computer и My.User  
 В следующем примере демонстрируется получение информации с использованием объектов `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 Помимо получения информации, члены, доступные через эти три объекта, также позволяют вызывать методы, связанные с этим объектом.  Например, с помощью `My.Computer` можно обращаться к различным методам управления файлами и редактирования реестра.  
  
 Файловый ввод\-вывод выполняется значительно проще и быстрее с помощью объекта `My`, включающего разнообразные методы и свойства для управления файлами, каталогами и дисками.  Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет читать данные из больших структурированных файлов, в которых содержатся поля с разделителями или поля фиксированной ширины.  В этом примере `TextFieldParser` `reader` открывается для чтения данных из файла `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` позволяет изменять язык и региональные параметры для приложения.  В следующем примере демонстрируется вызов этого метода.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)