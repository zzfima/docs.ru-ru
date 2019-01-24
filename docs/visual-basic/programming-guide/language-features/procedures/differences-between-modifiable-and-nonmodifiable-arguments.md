---
title: Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 06f3009d984f7a303a0ee6e8d529a3ff60900fbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498691"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
При вызове процедуры, обычно передается один или несколько аргументов к нему. Каждый аргумент соответствует базовому элементу программирования. Базовые элементы и сами аргументы может быть либо изменяемыми либо неизменяемыми.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Изменяемые и неизменяемые элементы  
 Программный элемент может быть либо *изменяемого элемента*, который может менять свое значение, или *неизменяемым*, который имеет фиксированное значение после его создания.  
  
 В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.  
  
|Изменяемые элементы|Неизменяемые элементы|  
|-------------------------|----------------------------|  
|Локальные переменные (объявленные внутри процедур), включая объектные переменные, доступные только для чтения|Переменные только для чтения, поля и свойства|  
|Поля (переменные-члены модулей, классов и структур), доступные только для чтения|Константы и литералы|  
|Свойства, доступные только для чтения|Члены перечисления|  
|Элементы массива|Выражения (даже если их элементы являются изменяемыми)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Аргументами modifiable и Nonmodifiable  
 Объект *изменяемые аргумент* — один с изменяемым базового элемента. Вызывающий код может хранить новое значение в любое время, и если передается аргумент [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), код в процедуру также можно изменить элемент в вызывающем коде.  
  
 Объект *неизменяемого аргумента* базовой неизменяемым или он передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Процедура не может изменить элемент в вызывающем коде, даже если он является изменяемым. Если он является неизменяемым, в вызывающем коде нельзя изменять.  
  
 Вызванная процедура может изменить свою локальную копию неизменяемого аргумента, но это изменение не влияет на базовый элемент в вызывающем коде.  
  
## <a name="see-also"></a>См. также
- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Практическое руководство. Принудительная передаваться по значению аргумента](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
