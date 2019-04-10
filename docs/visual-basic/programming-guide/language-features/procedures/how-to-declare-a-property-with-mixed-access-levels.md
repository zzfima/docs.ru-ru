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
ms.openlocfilehash: e899b57e02f492b0e4909aca84c069e5b7688618
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339818"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)
Если вы хотите, чтобы `Get` и `Set` процедуры в свойство, чтобы иметь различные уровни доступа, можно использовать менее строгий уровень в `Property` инструкции и более строгий уровень в любом `Get` или `Set` инструкция. Вы можете использовать смешанным уровнем доступа для свойства, определенные части кода, чтобы иметь возможность получить значение свойства, а другие части кода, чтобы иметь возможность изменить значение.  
  
 Дополнительные сведения об уровнях доступа см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Для объявления свойства со смешанным уровнем доступа  
  
1. Объявите свойство обычным способом и укажите менее строгий уровень доступа (такие как `Public`) в `Property` инструкции.  
  
2. Объявление любого `Get` или `Set` процедуру, указав более строгий уровень доступа (такие как `Friend`).  
  
3. Не указывайте уровень доступа на другие процедуры свойства. Предполагается уровень доступа, объявленные в `Property` инструкции. Можно ограничить доступ только к одной из процедур свойства.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     В приведенном выше примере `Get` процедуры имеет те же `Protected` доступа, что и само свойство, хотя `Set` процедура имеет `Private` доступа. Класс, производный от `employee` может считывать `salary` значение, но только `employee` класс может установить его.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создание свойства](./how-to-create-a-property.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
- [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)
