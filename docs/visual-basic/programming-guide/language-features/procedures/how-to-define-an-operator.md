---
title: Практическое руководство. Определение оператора
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
ms.openlocfilehash: b99af8ff4d5428f1749bfc1a4c51a136f12405ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344865"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Практическое руководство. Определение оператора (Visual Basic)
Если вы определили класс или структуру, то можете определить поведение стандартного оператора (например, `*`, `<>`или `And`), если один или оба операнда имеют тип класса или структуры.  
  
 Определите стандартный оператор в качестве процедуры оператора внутри класса или структуры. Все процедуры оператора должны быть `Public` `Shared`.  
  
 Определение оператора для класса или структуры также называется *перегрузкой* оператора.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется оператор `+` для структуры с именем `height`. Структура использует высоту, измеряемую в футах и дюймах. Один *дюйм* — 2,54 сантиметра, а *одна —* 12 дюймов. Чтобы обеспечить нормализованные значения (дюймы < 12,0), конструктор выполняет арифметический расчет по *модулю* 12. Оператор `+` использует конструктор для создания нормализованных значений.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Вы можете проверить структуру `height` с помощью следующего кода.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>См. также

- [Процедуры операторов](./operator-procedures.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
- [Оператор Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Практическое руководство. Объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Оператор Mod](../../../../visual-basic/language-reference/operators/mod-operator.md)
