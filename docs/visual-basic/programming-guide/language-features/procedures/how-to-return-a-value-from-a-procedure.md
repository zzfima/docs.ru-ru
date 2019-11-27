---
title: Практическое руководство. Возврат значения из процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346030"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Практическое руководство. Возврат значения из процедуры (Visual Basic)
`Function` процедура возвращает значение в вызывающий код, выполняя инструкцию `Return` или выполняя инструкцию `Exit Function` или `End Function`.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Возврат значения с помощью оператора return  
  
1. Поместите оператор `Return` в точку завершения задачи процедуры.  
  
2. Используйте ключевое слово `Return` с выражением, которое возвращает значение, которое необходимо вернуть в вызывающий код.  
  
3. В одной и той же процедуре можно использовать несколько операторов `Return`.  
  
     Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника и возвращает ее в вызывающий код.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     В следующем примере показан типичный вызов `hypotenuse`, в котором хранится возвращаемое значение.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Возврат значения с помощью функции exit или функции End  
  
1. По крайней мере в одном месте процедуры `Function` присвойте значение имени процедуры.  
  
2. При выполнении инструкции `Exit Function` или `End Function` Visual Basic возвращает последнее значение, назначенное имени процедуры.  
  
3. В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.  
  
4. В `Function`ной процедуре можно использовать только одну инструкцию `End Function`.  
  
     Дополнительные сведения и пример см. в разделе "возвращаемое значение" в [операторе Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md)
- [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
