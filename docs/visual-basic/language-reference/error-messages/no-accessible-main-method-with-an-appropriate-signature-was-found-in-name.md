---
title: "В &lt;имя&gt; не найдено доступного метода Main с подходящей подписью | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30737"
  - "vbc30737"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30737"
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# В &lt;имя&gt; не найдено доступного метода Main с подходящей подписью
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Для приложений командной строки должна быть определена `Sub Main`.  `Main` должна быть объявлена как `Public Shared`, если она определена в классе, или как `Public`, если она определена в модуле.  
  
 Дополнительные сведения по `Main` см. в разделе ["Hello, World", версия на языке Visual Basic](http://msdn.microsoft.com/ru-ru/9d030b60-e148-4366-a462-69532f02294c).  
  
 **Идентификатор ошибки:** BC30737  
  
### Чтобы исправить эту ошибку  
  
-   Определите процедуру `Public Sub Main` для проекта.  Объявите ее с доступом `Shared` только в том случае, если она определяется внутри класса.  
  
## См. также  
 ["Hello, World", версия на языке Visual Basic](http://msdn.microsoft.com/ru-ru/9d030b60-e148-4366-a462-69532f02294c)   
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)