---
title: "Неверный номер записи | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID63"
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Неверный номер записи
Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject` или `FilePutObject` меньше или равен нулю.  
  
### Исправление ошибки  
  
1.  Проверьте вычисления, используемые при формировании номера записи. Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей. Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.  
  
## См. также  
 [Оператор Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)