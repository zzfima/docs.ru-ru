---
title: "Sub или Function не определена (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID35"
dev_langs: 
  - "VB"
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Sub или Function не определена (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Sub` или `Function` должна быть определена, чтобы ее можно было вызывать.  Возможные причины этой ошибки:  
  
-   Неправильное написание имени процедуры.  
  
-   Попытка вызова процедуры из другого проекта без явного добавления ссылки на этот проект в диалоговом окне **Ссылки**.  
  
-   Задание процедуры, которая невидима для вызывающей процедуры.  
  
-   Объявление процедуры динамической библиотеки Windows \(DLL\) или процедуры из источника кода Macintosh, которые не содержатся в указанной библиотеке или источнике кода.  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте правильность написания имени процедуры.  
  
2.  Найдите имя проекта, содержащего процедуру, которую необходимо вызвать, в диалоговом окне **Ссылки**.  Если имя этого проекта не отображается, нажмите кнопку **Обзор**, чтобы выполнить поиск этого имени.  Установите флажок слева от имени проекта и нажмите кнопку **ОК**.  
  
3.  Проверьте имя процедуры.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Управление ссылками в проекте](/visual-studio/ide/managing-references-in-a-project)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)