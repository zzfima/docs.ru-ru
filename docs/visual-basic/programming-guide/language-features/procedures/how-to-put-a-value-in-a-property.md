---
title: "Практическое руководство: поместить значение в свойстве (Visual Basic) | Документы Microsoft"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: e3b2336589b525756a92cb3e26ab6c1950118b01
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Практическое руководство. Запись значения в свойство (Visual Basic)
Сохраните значение в свойстве, помещая имя свойства слева от оператора присваивания.  
  
 Свойство `Set` процедура сохраняет значение, но вы не вызывается явно. Свойство так же, как переменную. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]делает вызовы процедур свойств.  
  
### <a name="to-store-a-value-in-a-property"></a>Для хранения значений в свойстве  
  
1.  Используйте имя свойства слева от оператора присваивания.  
  
     В следующем примере задается значение [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` свойство полдень, неявно вызывая его `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures&11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов. Если не указано никаких аргументов, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
4.  Значение, созданное в правой части оператора присваивания, хранится в свойстве.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>   
 [Процедуры свойств](./property-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)   
 [Практическое руководство: создание свойства](./how-to-create-a-property.md)   
 [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md)   
 [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
