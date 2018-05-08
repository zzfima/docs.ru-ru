---
title: Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)
Если вы хотите `Get` и `Set` процедуры свойства для имеют разные уровни доступа, можно использовать менее строгий уровень в `Property` инструкции и более строгий уровень в любом `Get` или `Set` инструкция. Смешанные уровни доступа используются в свойстве, когда некоторые части кода, чтобы иметь возможность получить значение свойства, а другие части кода, чтобы иметь возможность изменить значение.  
  
 Дополнительные сведения об уровнях доступа см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Для объявления свойства со смешанным уровнем доступа  
  
1.  Объявите свойство обычным способом и укажите менее строгий уровень доступа (такие как `Public`) в `Property` инструкции.  
  
2.  Объявление любого `Get` или `Set` процедуру, указав более строгий уровень доступа (такие как `Friend`).  
  
3.  Не указывайте уровень доступа для процедуры свойства. Предполагается, что уровень доступа, объявленные в `Property` инструкции. Можно ограничить доступ только на одном из процедур свойства.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     В приведенном выше примере `Get` процедуры имеет те же `Protected` доступ как к самому свойству, пока `Set` процедура имеет `Private` доступа. Класс, производный от `employee` можно прочитать `salary` значение, но только `employee` класс может установить его.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)  
 [Практическое руководство. Создание свойства](./how-to-create-a-property.md)  
 [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)  
 [Как: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)  
 [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
