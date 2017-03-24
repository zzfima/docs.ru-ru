---
title: "Эффективное сочетание операторов (Visual Basic) | Microsoft Docs"
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
  - "выражения [Visual Basic], сложный"
  - "выражения [Visual Basic], операторы"
  - "выражения [Visual Basic], круглые скобки"
  - "числовые выражения"
  - "операторы [Visual Basic], ассоциативность"
  - "операторы [Visual Basic], сложные выражения"
  - "операторы [Visual Basic], приоритет"
  - "круглые скобки, сложные выражения"
  - "код Visual Basic, выражения"
  - "код Visual Basic, операторы"
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Эффективное сочетание операторов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Сложные выражения могут содержать большое количество различных операторов.  Это показано в приведенном ниже примере.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Создание сложных выражений, таких как в предыдущем примере, требует глубокого понимания правил приоритета операторов.  Дополнительные сведения см. в разделе [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Выражения в скобках  
 Часто возникает необходимость выполнения операций в порядке, отличном от порядка, заданного приоритетом операторов.  Рассмотрим следующий пример.  
  
 `x = z * y + 4`  
  
 В этом примере `z` умножается на `y`, а затем к результату добавляется `4`.  Однако если требуется сложить `y` и `4` перед умножением на `z`, можно переопределить очередность выполнения с помощью скобок.  Если выражение заключено в скобки, оно вычисляется в первую очередь независимо от приоритета операторов.  Чтобы в предыдущем примере сначала выполнить сложение, нужно переписать его следующим образом:  
  
 `x = z * (y + 4)`  
  
 В этом примере `y` складывается с `4`, а затем сумма умножается на `z`.  
  
### Вложенные выражения в скобках  
 Для дальнейшего переопределения приоритетов можно окружать выражения скобками разных уровней.  Выражения, наиболее глубоко вложенные в скобки, вычисляются первыми, далее — следующие наиболее глубоко вложенные и т.д., и в заключение вычисляются выражения за пределами скобок.  Это показано в приведенном ниже примере.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 В указанном выше примере выражение `z + 2` вычисляется раньше, чем другие выражения в скобках.  Возведение в степень, обычно имеющее более высокий приоритет по сравнению со сложением и умножением, вычисляется в этом примере в последнюю очередь, поскольку другие выражения заключены в скобки.  
  
## См. также  
 [Арифметические операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Логические \(побитовые\) операторы](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Логические выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Сравнения значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Практическое руководство. Вычисление числовых значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)