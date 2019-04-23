---
title: Практическое руководство. Получение значения из свойства (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5e2676a0880092a78405fe5dafa0469161b85610
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302937"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Практическое руководство. Получение значения из свойства (Visual Basic)
Извлечь значение свойства, включая имена свойств в выражении.  
  
 Свойства `Get` процедура получает значение, но не нужно явно вызывать ее по имени. Используйте свойство так же, как переменную. Visual Basic выполняет вызовы процедур свойств.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Для извлечения значения из свойства  
  
1. Используйте имя свойства в выражении так же, используется имя переменной. Свойство можно использовать везде, где можно использовать переменную или константу.  
  
     -или-  
  
     Используйте имя свойства после равенства (`=`) войдите в операторе присваивания.  
  
     В следующем примере считывается значение Visual Basic `Now` свойство, неявно вызова его `Get` процедуры.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов. Если аргументы не используются, скобки можно опустить.  
  
3. Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.  
  
 Значение свойства входит в выражение так же, как переменная или константа, или он хранится в переменной или свойству в левой части оператора присваивания.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md)
- [Практическое руководство. Создать свойство](./how-to-create-a-property.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Практическое руководство. Вызов процедуры свойства](./how-to-call-a-property-procedure.md)
- [Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)
