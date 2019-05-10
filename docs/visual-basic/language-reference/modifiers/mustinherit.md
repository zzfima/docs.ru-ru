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
ms.openlocfilehash: 05b1e6b646c519216eba2d4f0df7a3e32f3dafbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661263"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Указывает, что класс может использоваться только в качестве базового класса, и что не удается создать объект непосредственно из него.  
  
## <a name="remarks"></a>Примечания  
 Цель *базового класса* (также известный как *абстрактного класса*) заключается в определении функции, общие для всех классов, производных от него. Это экономит производные классы от необходимости переопределять Общие элементы. В некоторых случаях эти общие функциональные возможности не недостаточно полна, чтобы сделать подходящий объект, и каждый производный класс определяет отсутствующие функциональные возможности. В этом случае требуется много кода для создания объектов только из производных классов. Использовании `MustInherit` в базовом классе, это обеспечить.  
  
 Другим использованием `MustInherit` класс является ограничение переменной для набора связанных классов. Можно определить базовый класс и производные от него все эти связанные классы. Базовый класс не требуется ли предоставлять любые функции, общие для всех производных классов, но его можно использовать в качестве фильтра для присвоения значений переменным. Если код объявляет переменную как базовый класс, Visual Basic позволяет присвоить переменной только объект из одного из производных классов.  
  
 .NET Framework определяет несколько `MustInherit` классов, между ними <xref:System.Array>, <xref:System.Enum>, и <xref:System.ValueType>. <xref:System.ValueType> приведен пример базового класса, который ограничивает переменную. Все типы значений являются производными от <xref:System.ValueType>. Если объявить переменную как <xref:System.ValueType>, этой переменной можно назначить только типы значений.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** Можно использовать `MustInherit` только в `Class` инструкции.  
  
- **Комбинированные модификаторы.** Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.  
  
## <a name="example"></a>Пример  
 В следующем примере показано принудительное наследование и переопределение. Базовый класс `shape` определяет переменную `acrossLine`. Классы `circle` и `square` являются производными от `shape`. Они наследуют определение `acrossLine`, но должны определять функцию `area` так, как это вычисление отличается для каждого вида фигуры.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Можно объявить `shape1` и `shape2` типа `shape`. Тем не менее, не удается создать объект из `shape` так, как у него нет функцию `area` и помечается `MustInherit`.  
  
 Так как они будут объявлены как `shape`, переменные `shape1` и `shape2` доступны только для объектов из производных классов `circle` и `square`. Visual Basic не поддерживает назначение любого другого объекта эти переменные, которая предоставляет высокий уровень безопасности типов.  
  
## <a name="usage"></a>Использование  
 `MustInherit` Модификатор может использоваться в этом контексте:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
