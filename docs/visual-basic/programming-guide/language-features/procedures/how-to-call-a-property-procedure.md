---
title: "Практическое руководство: вызов процедуры свойства (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7dd3d53f602886f65c951de34b915b2672b1a817
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Практическое руководство. Вызов процедуры свойства (Visual Basic)
Вызов процедуры свойства хранения значения свойства или извлечения его значения. Доступ к свойству так же, можно получить доступ к переменной.  
  
 Свойство `Set` процедура сохраняет значение и его `Get` процедура получает значение. Тем не менее не вызывается явным образом эти процедуры по имени. Свойство в операторе присваивания или выражении так же, как хранить или извлекать значения переменной. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]делает вызовы процедур свойств.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Для вызова процедуры Get свойства  
  
1.  Используйте имя свойства в выражении так же, как имя переменной. Можно использовать свойство везде, где можно использовать переменную или константу.  
  
     -или-  
  
     Используйте имя свойства после равенства (`=`) входа в операторе присваивания.  
  
     В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>Свойства, неявно вызывая его `Get` процедуры.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
  
     [!code-vb[VbVbalrDateProperties&#4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа или хранится в переменной или свойстве в левой части оператора присваивания.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Чтобы вызвать свойство процедуры Set  
  
1.  Используйте имя свойства слева от оператора присваивания.  
  
     В следующем примере задается значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>Свойства, неявно вызова `Set` процедуры.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
  
     [!code-vb[VbVbcnProcedures&11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение, созданное в правой части оператора присваивания, хранится в свойстве.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](./property-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)   
 [Практическое руководство: создание свойства](./how-to-create-a-property.md)   
 [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md)   
 [Практическое руководство: получение значения из свойства](./how-to-get-a-value-from-a-property.md)   
 [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)
