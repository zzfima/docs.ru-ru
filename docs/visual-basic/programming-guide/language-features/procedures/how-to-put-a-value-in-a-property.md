---
title: Практическое руководство. Запись значения в свойства (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 34348d57db0875d9c2c6192ac754b4f83f515ac4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965474"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Практическое руководство. Запись значения в свойства (Visual Basic)
Для сохранения значения в свойство, помещая имя свойства в левой части оператора присваивания.  
  
 Свойства `Set` процедура сохраняет значение, но не нужно явно вызывать ее по имени. Используйте свойство так же, как переменную. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-store-a-value-in-a-property"></a>Для хранения значения в свойстве  
  
1.  Используйте имя свойства в левой части оператора присваивания.  
  
     В следующем примере значение Visual Basic `TimeOfDay` свойство полдень, неявно вызова его `Set` процедуры.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2.  Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
4.  Значение, созданное в правой части оператора присваивания хранится в свойстве.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создать свойство](./how-to-create-a-property.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
