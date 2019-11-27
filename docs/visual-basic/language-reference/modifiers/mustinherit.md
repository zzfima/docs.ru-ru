---
title: MustInherit
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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351501"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Указывает, что класс может использоваться только в качестве базового класса и не может создавать объект непосредственно из него.  
  
## <a name="remarks"></a>Примечания  
 Целью *базового класса* (также известного как *абстрактный класс*) является определение функций, общих для всех классов, производных от него. Это позволяет сохранить производные классы от необходимости переопределять общие элементы. В некоторых случаях эта общая функциональность не является достаточно полной для создания пригодного для использования объекта, и каждый производный класс определяет недостающие функциональные возможности. В этом случае необходимо, чтобы код, создающий объекты, был создан только из производных классов. Для этого используйте `MustInherit` в базовом классе.  
  
 Другое использование класса `MustInherit` заключается в ограничении переменной набором связанных классов. Можно определить базовый класс и получить от него все связанные с ним классы. Базовый класс не обязан предоставлять функциональные возможности, общие для всех производных классов, но он может служить фильтром для присвоения значений переменным. Если в используемом коде объявляется переменная в качестве базового класса, Visual Basic позволяет назначить этой переменной только один из производных классов.  
  
 .NET Framework определяет несколько классов `MustInherit`, между ними <xref:System.Array>, <xref:System.Enum>и <xref:System.ValueType>. <xref:System.ValueType> является примером базового класса, который ограничивают переменную. Все типы значений являются производными от <xref:System.ValueType>. Если переменная объявляется как <xref:System.ValueType>, то этой переменной можно назначить только типы значений.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** `MustInherit` можно использовать только в инструкции `Class`.  
  
- **Комбинированные модификаторы.** Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.  
  
## <a name="example"></a>Пример  
 В следующем примере показано принудительное наследование и принудительное переопределение. Базовый класс `shape` определяет переменную `acrossLine`. Классы `circle` и `square` являются производными от `shape`. Они наследуют определение `acrossLine`, но они должны определять функцию `area` поскольку вычисление для каждого вида формы различается.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Можно объявить `shape1` и `shape2` типа `shape`. Однако нельзя создать объект из `shape`, так как в нем отсутствуют функциональные возможности функции `area` и он помечен как `MustInherit`.  
  
 Поскольку они объявляются как `shape`, переменные `shape1` и `shape2` ограничиваются объектами из производных классов `circle` и `square`. Visual Basic не позволяет назначать другим объектам эти переменные, что обеспечивает высокий уровень безопасности типов.  
  
## <a name="usage"></a>Использование  
 Модификатор `MustInherit` можно использовать в этом контексте:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>См. также

- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
