---
title: "Практическое руководство. Определение оператора (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51921ee38204fd528ed19436806fc9433abbdc5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-an-operator-visual-basic"></a>Практическое руководство. Определение оператора (Visual Basic)
Если вы определили класс или структура, можно определить поведение стандартного оператора (например, `*`, `<>`, или `And`) Если один или оба операнда имеет тип класса или структуры.  
  
 Определите стандартного оператора как процедура оператора в классе или структуре. Все процедуры оператора должны быть `Public` `Shared`.  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `+` вызван оператор для структуры `height`. Структура использует высоту в метрах и дюйма. Один *дюйма* 2,54 сантиметра и одна *foot* -12 дюймов. Чтобы обеспечить нормализованные значения (в дюймах < 12.0), конструктор выполняет *остаток от деления* арифметические 12. `+` Оператор использует конструктор для создания нормализованных значений.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Можно проверить структуру `height` следующим кодом.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>См. также  
 [Процедуры операторов](./operator-procedures.md)  
 [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)  
 [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)  
 [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)  
 [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md)
