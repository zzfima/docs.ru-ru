---
title: Практическое руководство. Запись значения в свойство (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00303b290e324612ad3ac7af673690b4cf4e15
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Практическое руководство. Запись значения в свойство (Visual Basic)
Для сохранения значения в свойство, помещая имя свойства слева от оператора присваивания.  
  
 Свойство `Set` процедура сохраняет значение, но вы не вызывается явно. Свойство так же, как переменную. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-store-a-value-in-a-property"></a>Для хранения значений в свойстве  
  
1.  Используйте имя свойства слева от оператора присваивания.  
  
     В следующем примере задается значение Visual Basic `TimeOfDay` свойство полдень, неявно вызывая его `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
4.  Значение, созданное в правой части оператора присваивания, хранится в свойстве.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [Процедуры свойств](./property-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)  
 [Практическое руководство. Создание свойства](./how-to-create-a-property.md)  
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
