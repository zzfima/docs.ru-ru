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
ms.openlocfilehash: 2b60d732b260ad0477946e41ece4cd182de541ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Различия между аргументами Modifiable и Nonmodifiable (Visual Basic)
При вызове процедуры обычно передаваемого один или несколько аргументов. Каждый аргумент соответствует базовому элементу программирования. Базовые элементы и аргументы сами могут быть либо изменяемыми либо неизменяемыми.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Изменяемые и неизменяемые элементы  
 Программный элемент может быть либо *изменяемого элемента*, которого можно менять свое значение, или *неизменяемым*, который имеет фиксированное значение после его создания.  
  
 В следующей таблице перечислены изменяемые и неизменяемые элементы программирования.  
  
|Изменяемые элементы|Неизменяемые элементы|  
|-------------------------|----------------------------|  
|Локальные переменные (объявленные внутри процедур), включая объектные переменные, доступные только для чтения|Переменные только для чтения, поля и свойства|  
|Поля (переменные-члены модулей, классы и структуры), доступные только для чтения|Константы и литералы|  
|Свойства, доступные только для чтения|Члены перечисления|  
|Элементы массива|Выражения (даже если их элементы являются изменяемыми)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Изменяемые и неизменяемые аргументы  
 Объект *изменяемый аргумент* с изменяемым базового элемента. Вызывающий код может хранить новое значение в любое время, и если передать аргумент [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), код в процедуре сможет изменить базовый элемент в вызывающем коде.  
  
 Объект *неизменяемого аргумента* имеет базовый неизменяемым или параметром, переданным [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Процедура не может изменить базовый элемент в вызывающем коде, даже если он является изменяемым. Если он является неизменяемым, в вызывающем коде нельзя изменять.  
  
 Вызванная процедура может изменить свою локальную копию неизменяемого аргумента, но это изменение не затронет базовый элемент в вызывающем коде.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
