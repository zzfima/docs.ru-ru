---
title: Различия между изменяемыми и неизменяемыми аргументами
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 989795ee2cdd3a78b71bad4d95cf9b384c2719bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341388"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
При вызове процедуры в нее обычно передается один или несколько аргументов. Каждый аргумент соответствует базовому программному элементу. Как базовые элементы, так и сами аргументы могут быть либо изменяемыми, либо неизменяемыми.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Изменяемые и неизменяемые элементы  
 Программным элементом может быть *изменяемый элемент*, для которого может быть изменено значение, или *неизменяемый элемент*, имеющий фиксированное значение после создания.  
  
 В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.  
  
|Изменяемые элементы|Неизменяемые элементы|  
|-------------------------|----------------------------|  
|Локальные переменные (объявленные в процедурах), включая переменные объекта, за исключением только для чтения|Переменные, поля и свойства только для чтения|  
|Поля (переменные-члены модулей, классов и структур), кроме только для чтения|Константы и литералы|  
|Свойства, кроме "только для чтения"|Члены перечисления|  
|Элементы массива|Выражения (даже если их элементы являются изменяемыми)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Изменяемые и неизменяемые аргументы  
 *Изменяемый аргумент* — это один из изменяемых базовых элементов. Вызывающий код может сохранить новое значение в любое время, и при передаче аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)код в процедуре также может изменить базовый элемент в вызывающем коде.  
  
 *Неизменяемый аргумент* либо имеет неизменяемый базовый элемент, либо передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Процедура не может изменить базовый элемент в вызывающем коде, даже если это изменяемый элемент. Если это неизменяемый элемент, то сам вызывающий код не может изменить его.  
  
 Вызванная процедура может изменить свою локальную копию неизменяемого аргумента, но это изменение не влияет на базовый элемент в вызывающем коде.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
