---
title: Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648441"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)
Вы используете `Function` процедуры возвращают значение вызывающему коду.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение  
  
1.  Вне любых других процедур используйте `Function` инструкции, за которой следует `End Function` инструкции.  
  
2.  В `Function` инструкции, выполните `Function` ключевого слова with имя процедуры, а затем список параметров в круглых скобках.  
  
3.  Круглые скобки, используя `As` предложений, чтобы указать тип данных возвращаемого значения.  
  
4.  Поместите операторы кода процедуры между `Function` и `End Function` инструкции.  
  
5.  Используйте `Return` инструкцию, чтобы возвращать значение вызывающему коду.  
  
     Следующие `Function` процедуры рассчитывается длинной стороны, гипотенуза прямоугольного треугольника, заданы значения для двух других сторон.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     В примере показан типичный вызов `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)  
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
