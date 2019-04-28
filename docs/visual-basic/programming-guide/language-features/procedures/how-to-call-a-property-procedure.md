---
title: Практическое руководство. Вызов процедуры свойства (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864368"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры свойства (Visual Basic)
Вызов процедуры свойства хранить значение в свойстве или его значение было получено. Доступ к свойству так же, можно получить доступ к переменной.  
  
 Свойства `Set` процедура сохраняет значение и его `Get` процедура получает значение. Тем не менее не вызывается явным образом эти процедуры по имени. Свойство в операторе присваивания или выражение, так же, как хранить или получить значение переменной. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Чтобы вызвать процедуру свойства Get  
  
1. Используйте имя свойства в выражении так же, используется имя переменной. Свойство можно использовать везде, где можно использовать переменную или константу.  
  
     -или-  
  
     Используйте имя свойства после равенства (`=`) войдите в операторе присваивания.  
  
     В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойство, неявно вызова его `Get` процедуры.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3. Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа, или он хранится в переменной или свойству в левой части оператора присваивания.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Чтобы вызвать свойство процедуры Set  
  
1. Используйте имя свойства в левой части оператора присваивания.  
  
     В следующем примере значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойство, неявно вызова `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3. Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение, созданное в правой части оператора присваивания хранится в свойстве.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создать свойство](./how-to-create-a-property.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
- [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)
