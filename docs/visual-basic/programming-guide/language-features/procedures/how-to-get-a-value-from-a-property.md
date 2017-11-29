---
title: "Практическое руководство. Получение значения из свойства (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cde5408ea09398a79a3da01ae9b2d0202c58eaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Практическое руководство. Получение значения из свойства (Visual Basic)
Получить значение свойства, включая имя свойства в выражении.  
  
 Свойство `Get` процедура получает значение, но вы не вызывается явно. Свойство так же, как переменную. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]делает вызовы процедур свойств.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Для извлечения значения из свойства  
  
1.  Используйте имя свойства в выражении так же, как имя переменной. Можно использовать свойство везде, где можно использовать переменную или константу.  
  
     -или-  
  
     Используйте имя свойства после равенства (`=`) войти в операторе присваивания.  
  
     В следующем примере считывается значение [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` свойства, неявно вызывая его `Get` процедуры.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа или он хранится в переменной или свойстве в левой части оператора присваивания.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)  
 [Практическое руководство. Создание свойства](./how-to-create-a-property.md)  
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
