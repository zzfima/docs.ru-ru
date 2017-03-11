---
title: "Ошибка при загрузке библиотеки DLL (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID48"
dev_langs: 
  - "VB"
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Ошибка при загрузке библиотеки DLL (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Динамически подключаемая библиотека \(DLL\) — это библиотека, заданная в предложении `Lib` оператора `Declare`.  Возможные причины этой ошибки:  
  
-   Файл не является исполняемой программой DLL.  
  
-   Файл не является файлом DLL Microsoft Windows.  
  
-   DLL ссылается на другую, не существующую DLL.  
  
-   Данной DLL или DLL, на которую есть ссылка, нет в каталоге, указанном в пути.  
  
### Чтобы исправить эту ошибку  
  
-   Если файл является исходным текстовым файлом и, следовательно, не является исполняемым файлом DLL, его следует скомпилировать и привязать к исполняемой форме DLL.  
  
-   Если файл не является DLL\-файлом Microsoft Windows, следует получить его эквивалент в Microsoft Windows.  
  
-   Если DLL ссылается на другую, не существующую DLL, следует получить DLL, на которую существует ссылка, и сделать ее доступной.  
  
-   Если данной DLL или DLL, на которую существует ссылка, нет в каталоге, указанном в пути, следует перенести DLL в каталог, на который указывает ссылка.  
  
## См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)