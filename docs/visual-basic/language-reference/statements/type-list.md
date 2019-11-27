---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 3f2aaa65293ed2bcc6c8eeb4bd77e49907d93425
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352779"
---
# <a name="type-list-visual-basic"></a>Список типов (Visual Basic)

Задает *Параметры типа* для *универсального* программного элемента. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра типа.

## <a name="syntax"></a>Синтаксис

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`genericmodifier`|Необязательный элемент. Может использоваться только в универсальных интерфейсах и делегатах. Ковариантность типа можно объявить с помощью ключевого слова [out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) или контравариантного с помощью ключевого слова [in](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) . См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Обязательно. Имя параметра типа. Это заполнитель, заменяемый определенным типом, предоставленным соответствующим аргументом типа.|
|`constraintlist`|Необязательный элемент. Список требований, ограничивающих тип данных, который можно указать для `typename`. При наличии нескольких ограничений заключите их в фигурные скобки (`{ }`) и разделите их запятыми. Список ограничений необходимо ввести с помощью ключевого слова [as](../../../visual-basic/language-reference/statements/as-clause.md) . Вы используете `As` только один раз, в начале списка.|

## <a name="remarks"></a>Примечания

Каждый универсальный программный элемент должен принимать по крайней мере один параметр типа. Параметр типа — это заполнитель для определенного типа ( *сконструированного элемента*), который клиентский код указывает при создании экземпляра универсального типа. Можно определить универсальный класс, структуру, интерфейс, процедуру или делегат.

Дополнительные сведения о том, когда следует определять универсальный тип, см. [в разделе Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Дополнительные сведения об именах параметров типов см. в разделе [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Правила

- **Скобки.** Если вы представите список параметров типа, необходимо заключить его в круглые скобки и ввести в список ключевое слово [of](../../../visual-basic/language-reference/statements/of-clause.md) . Вы используете `Of` только один раз, в начале списка.

- **Учитывая.** Список *ограничений* для параметра типа может включать в себя следующие элементы в любом сочетании:

  - Любое количество интерфейсов. Указанный тип должен реализовывать каждый интерфейс в этом списке.

  - Не более одного класса. Указанный тип должен наследоваться от этого класса.

  - Ключевое слово `New`. Предоставленный тип должен предоставлять конструктор без параметров, к которому имеет доступ универсальный тип. Это полезно, если параметр типа ограничивается одним или несколькими интерфейсами. Тип, реализующий интерфейсы, не обязательно предоставляет конструктор, и в зависимости от уровня доступа конструктора код в универсальном типе может не иметь возможности получить к нему доступ.

  - Либо ключевое слово `Class`, либо ключевое слово `Structure`. Ключевое слово `Class` ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был ссылочным типом, например строкой, массивом или делегатом, или объектом, созданным из класса. Ключевое слово `Structure` ограничивает параметр универсального типа, требуя, чтобы любой передаваемый аргумент типа был типом значения, например структурой, перечислением или простым типом данных. В одном `constraintlist`нельзя включать как `Class`, так и `Structure`.

  Указанный тип должен отвечать всем требованиям, включенным в `constraintlist`.

  Ограничения для каждого параметра типа не зависят от ограничений для других параметров типа.

## <a name="behavior"></a>Поведение

- **Подстановка во время компиляции.** При создании сконструированного типа на основе универсального программного элемента вы предоставляете определенный тип для каждого параметра типа. Компилятор Visual Basic замещает указанный тип для каждого вхождения `typename` в пределах универсального элемента.

- **Отсутствие ограничений.** Если не указать какие-либо ограничения на параметр типа, код будет ограничен операциями и элементами, поддерживаемыми [типом данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md) для этого параметра типа.

## <a name="example"></a>Пример

В следующем примере показано определение каркаса универсального класса Dictionary, включая скелет функции для добавления новой записи в словарь.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Пример

Поскольку `dictionary` является универсальным, код, который использует его, может создавать разнообразные объекты, каждый из которых имеет одинаковые функциональные возможности, но работает с другим типом данных. В следующем примере показана строка кода, создающая объект `dictionary` с `String` записями и ключами `Integer`.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Пример

В следующем примере показано эквивалентное определение скелета, созданное в предыдущем примере.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>См. также

- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Ковариация и контрвариантность](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
