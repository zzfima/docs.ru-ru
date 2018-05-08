---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Указывает, что класс может использоваться только как базовый класс и что невозможно создать объект непосредственно из него.  
  
## <a name="remarks"></a>Примечания  
 Назначение *базового класса* (также известный как *абстрактного класса*) заключается в определении функции, общие для всех классов, производных от него. Это экономит производные классы от необходимости переопределять Общие элементы. В некоторых случаях эти общие функциональные возможности не завершено, чтобы сделать подходящий объект, и каждый производный класс определяет отсутствующие функциональные возможности. В этом случае требуется много кода для создания объектов только из производных классов. Вы используете `MustInherit` базового класса, чтобы этого добиться.  
  
 Другое использование оператора `MustInherit` класса является ограничение переменной до набора связанных классов. Можно определить базовый класс и производные от него все эти связанные классы. Базовый класс не требуется для предоставления функциональных возможностей, общих для всех производных классов, но его можно использовать в качестве фильтра для присвоения значений переменным. Если код объявляет переменную как базовый класс, Visual Basic можно присвоить переменной только объект из одного из производных классов.  
  
 Платформа .NET Framework определяет несколько `MustInherit` классы, среди них <xref:System.Array>, <xref:System.Enum>, и <xref:System.ValueType>. <xref:System.ValueType> Примером может служить базового класса, который ограничивает переменную. Все типы значений являются производными от <xref:System.ValueType>. Если объявить переменную как <xref:System.ValueType>, этой переменной можно назначить только типы значений.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `MustInherit` только в `Class` инструкции.  
  
-   **Комбинированные модификаторы.** Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как принудительное наследование и переопределение. Базовый класс `shape` определяет переменную `acrossLine`. Классы `circle` и `square` являются производными от `shape`. Они наследуют определение `acrossLine`, но должны определять функции `area` так, как это вычисление, отличается для каждого вида фигуры.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 Можно объявить `shape1` и `shape2` типа `shape`. Тем не менее, не удается создать объект из `shape` , так как он не имеет функцию `area` и помечается `MustInherit`.  
  
 Так как они были объявлены как `shape`, переменные `shape1` и `shape2` доступны только для объектов из производных классов `circle` и `square`. Visual Basic не можно назначать любой другой объект на эти переменные, что обеспечивает высокий уровень безопасности типов.  
  
## <a name="usage"></a>Использование  
 `MustInherit` Модификатор может использоваться в этом контексте:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
