---
title: Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: ce0010762374baf5b19ab2e64f50e12fefda2dee
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966982"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Практическое руководство. Создание процедуры, возвращающей значение (Visual Basic)
Использовании `Function` процедуры возвращают значение в вызывающий код.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Создание процедуры, возвращающей значение  
  
1.  Вне любых других процедур используйте `Function` , применив инструкцию `End Function` инструкции.  
  
2.  В `Function` инструкции, следуйте `Function` ключевое слово с именем процедуры, а затем список параметров в круглых скобках.  
  
3.  Круглые скобки, используя `As` предложение, чтобы указать тип данных возвращаемого значения.  
  
4.  Поместите операторы кода процедуры между `Function` и `End Function` инструкций.  
  
5.  Используйте `Return` инструкция возвращает значение вызывающему коду.  
  
     Следующие `Function` процедура вычисляет самая длинная сторона гипотенузы прямоугольного треугольника, значения для двух других сторон.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     В следующем примере показано типичный вызов `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также
- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Практическое руководство. Возвращение значения из процедуры](./how-to-return-a-value-from-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
