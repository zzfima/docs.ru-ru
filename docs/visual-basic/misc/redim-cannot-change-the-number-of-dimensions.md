---
title: "ReDim не может изменять размерность | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrArray_RankMismatch"
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# ReDim не может изменять размерность
Предпринята попытка использования оператора `ReDim` для изменения ранга \(размерности\) массива. Оператор `ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
### Исправление ошибки  
  
-   Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## См. также  
 [НЕ В СБОРКЕ. Обзор массивов в Visual Basic](http://msdn.microsoft.com/ru-ru/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [НЕ В СБОРКЕ. Многомерные массивы в Visual Basic](http://msdn.microsoft.com/ru-ru/d92cad25-07e2-4d79-8ea4-ab269700f5de)   
 [Оператор ReDim](../../visual-basic/language-reference/statements/redim-statement.md)   
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)