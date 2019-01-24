---
title: Как выполнить Определение оператора (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: fb150298562c1ec91f73f3c8075f4f8a4fc20b27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679530"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Как выполнить Определение оператора (Visual Basic)
Если вы определили, класса или структуры, можно определить поведение стандартного оператора (такие как `*`, `<>`, или `And`) Если один или оба операнда имеет тип класса или структуры.  
  
 Определите стандартного оператора как процедура оператора в классе или структуре. Все процедуры оператора должны быть `Public` `Shared`.  
  
 Определение оператора в классе или структуре также называется *перегрузка* оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `+` вызывается оператор для структуры `height`. Структура использует высоту в футах и дюйма. Один *дюйм* — 2,54 сантиметра и одна *foot* — 12 дюймов. Чтобы обеспечить нормализованные значения (дюймы < 12.0), конструктор выполняет *остаток от деления* арифметические 12. `+` Оператор использует конструктор для создания нормализованных значений.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Вы можете проверить структуру `height` следующим кодом.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).  
  
## <a name="see-also"></a>См. также
- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Используйте класс, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
- [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md)
