---
title: "Аргумент NPer должен быть больше нуля | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrRate_NPerMustBeGTZero"
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Аргумент NPer должен быть больше нуля
Функция `NPer`, которая возвращает значение `Double`, определяющее количество периодов для ежегодного дохода на основе периодических фиксированных выплат и фиксированной процентной ставки, требует аргумент, значение которого больше нуля.  
  
### Исправление ошибки  
  
-   Проверьте правильность написания аргументов в выражении. Неправильно написанное имя переменной может привести к неявному созданию числовой переменной, которая инициализируется нулевым значением.  
  
-   Проверьте предыдущие операции с переменными в выражении, в особенности те, которые передавались в процедуру как аргументы из других процедур.  
  
## См. также  
 [НЕ В СБОРКЕ. Функция NPer](http://msdn.microsoft.com/ru-ru/56567d16-29f7-4928-b05f-b4cd56d4fd42)   
 [Передача аргументов по значению и по ссылке](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)