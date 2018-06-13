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
ms.openlocfilehash: 61d79b9ff99ec144a9c629872abd2a7e7ebda4d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654821"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры свойства (Visual Basic)
Вызов процедуры свойства хранения значения свойства или извлечения его значения. Доступ к свойству так же, как можно получить доступ к переменной.  
  
 Свойство `Set` процедура сохраняет значение и его `Get` процедура получает значение. Тем не менее не вызывается явным образом эти процедуры по имени. Свойство в операторе присваивания или выражении так же, как и при сохранении или получить значение переменной. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Вызов процедуры свойства Get  
  
1.  Используйте имя свойства в выражении так же, как имя переменной. Можно использовать свойство везде, где можно использовать переменную или константу.  
  
     - или -  
  
     Используйте имя свойства после равенства (`=`) войти в операторе присваивания.  
  
     В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойства, неявно вызывая его `Get` процедуры.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа или он хранится в переменной или свойстве в левой части оператора присваивания.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Для вызова свойства процедуры Set  
  
1.  Используйте имя свойства слева от оператора присваивания.  
  
     В следующем примере задается значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойства, неявно вызова `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение, созданное в правой части оператора присваивания, хранится в свойстве.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](./property-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)  
 [Практическое руководство. Создание свойства](./how-to-create-a-property.md)  
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)  
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)  
 [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)
