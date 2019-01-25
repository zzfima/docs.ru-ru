---
title: Как выполнить Вызов процедуры свойства (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 1f8871c2cc5126110fa849d42eed3d8edb3a03f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602576"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Как выполнить Вызов процедуры свойства (Visual Basic)
Вызов процедуры свойства хранить значение в свойстве или его значение было получено. Доступ к свойству так же, можно получить доступ к переменной.  
  
 Свойства `Set` процедура сохраняет значение и его `Get` процедура получает значение. Тем не менее не вызывается явным образом эти процедуры по имени. Свойство в операторе присваивания или выражение, так же, как хранить или получить значение переменной. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Чтобы вызвать процедуру свойства Get  
  
1.  Используйте имя свойства в выражении так же, используется имя переменной. Свойство можно использовать везде, где можно использовать переменную или константу.  
  
     - или -  
  
     Используйте имя свойства после равенства (`=`) войдите в операторе присваивания.  
  
     В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойство, неявно вызова его `Get` процедуры.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа, или он хранится в переменной или свойству в левой части оператора присваивания.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Чтобы вызвать свойство процедуры Set  
  
1.  Используйте имя свойства в левой части оператора присваивания.  
  
     В следующем примере значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойство, неявно вызова `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
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
