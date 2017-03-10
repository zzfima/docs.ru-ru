---
title: "Практическое руководство. Определение оператора (Visual Basic) | Microsoft Docs"
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
  - "перегрузка операторов"
  - "процедуры операторов, сведения о процедурах операторов"
  - "операторы [Visual Basic], определение"
  - "операторы [Visual Basic], перегрузка"
  - "процедуры, определение"
  - "процедуры, оператор"
  - "возвращаемые значения, Процедуры операторов"
  - "синтаксис, Процедуры операторов"
  - "код Visual Basic, операторы"
  - "код Visual Basic, процедуры"
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Практическое руководство. Определение оператора (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если определены класс или структура, то можно определить поведение стандартного оператора \(такого как `*`, `<>` или `And`\) при одном или двух относящихся в этому типу операндах.  
  
 Определите внутри класса или структуры стандартный оператор как процедуру оператора.  Все процедуры оператора должны быть`Public` `Shared`.  
  
 Определение оператора в классе или структуре называется также *перегрузкой* оператора.  
  
## Пример  
 В следующем примере определяется оператор `+` для структуры с именем `height`.  Структура использует высоту в футах и дюймах.  Один *дюйм* составляет 2,54 сантиметра, а один *фут* \- 12 дюймов.  Чтобы обеспечить нормализованные значения \(дюйм \<12.0\), конструктор выполняет арифметическое сложение *по модулю* 12.  Оператор `+` использует конструктор для создания нормализованных значений.  
  
 [!code-vb[VbVbcnProcedures#25](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-define-an-operator_1.vb)]  
  
 Можно проверить структуру  `height`  с помощью следующего кода.  
  
 [!code-vb[VbVbcnProcedures#26](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-define-an-operator_2.vb)]  
  
 Дополнительные сведения и примеры содержатся в [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## См. также  
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Практическое руководство. Вызов процедуры оператора](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Практическое руководство. Использование класса, в котором определяются операторы](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md)