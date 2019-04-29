---
title: Список типов (Visual Basic)
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
ms.openlocfilehash: d071e59d94e51ca55167983d0ee3098bd5c7dd8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698633"
---
# <a name="type-list-visual-basic"></a>Список типов (Visual Basic)

Указывает *параметры типа* для *универсального* программный элемент. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра типа.

## <a name="syntax"></a>Синтаксис

```
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Части

|Термин|Определение|
|---|---|
|`genericmodifier`|Необязательный параметр. Можно использовать только в универсальных интерфейсах и делегатах. Можно объявить тип ковариантным с помощью [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) ключевое слово или контравариантные с помощью [в](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) ключевое слово. См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Обязательный. Имя параметра типа. Это заполнитель, заменяется на определенный тип, предоставленный соответствующим аргументом типа.|
|`constraintlist`|Необязательный параметр. Список требований, ограничивающих тип данных, который может быть предоставлено `typename`. Если у вас есть несколько ограничений, заключайте их в фигурные скобки (`{ }`) и разделяйте их запятыми. Данные необходимо ввести список ограничений с [как](../../../visual-basic/language-reference/statements/as-clause.md) ключевое слово. Использовании `As` только один раз, в начале списка.|

## <a name="remarks"></a>Примечания

Каждый стандартный программный элемент необходимо выполнить хотя бы один параметр типа. Параметр типа является заполнителем для определенного типа ( *сконструированный элемент*), в коде клиента указывается при создании экземпляра универсального типа. Можно определить универсальный класс, структура, интерфейс, процедуру или делегат.

Дополнительные сведения о том, когда для определения универсального типа см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Дополнительные сведения о имена параметров-типов, см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Правила

- **Круглые скобки.** Если указать список параметров типа, его необходимо заключить в круглые скобки и данные необходимо ввести список с [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Использовании `Of` только один раз, в начале списка.

- **Ограничения.** Список *ограничения* для типа параметра можно включить следующие элементы в любой комбинации:

  - Любое число интерфейсов. Указанный тип должен реализовывать каждый интерфейс в этом списке.

  - Не более одного класса. Указанный тип должен наследовать от этого класса.

  - Ключевое слово `New`. Тип должен предоставлять конструктор без параметров, можно получить доступ к вашей универсального типа. Это полезно в том случае, если ограничения параметра типа, один или несколько интерфейсов. Тип, реализующий интерфейсы не обязательно предоставлять конструктор, и в зависимости от уровня доступа конструктора, код внутри универсального типа не может быть получить к ним доступ.

  - Либо `Class` ключевое слово или `Structure` ключевое слово. `Class` Ключевое слово ограничивает параметр универсального типа для требуют любой тип аргумента, переданного ему был ссылочным типом, например, строка, массив или делегат, или объект, созданный из класса. `Structure` Ключевое слово ограничивает параметр универсального типа для требуют, что любой тип аргумента, переданного ему был типом значения, например структуры, перечисления или простым типом данных. Нельзя включать оба `Class` и `Structure` в том же `constraintlist`.

  Указанный тип должен удовлетворять каждому требованию, добавляемых в `constraintlist`.

  Ограничения для каждого параметра типа не зависят от ограничений для других параметров типа.

## <a name="behavior"></a>Поведение

- **Подстановка во время компиляции.** При создании сконструированный тип из универсального элемента программирования, вам предоставляется определенный тип для каждого параметра типа. Компилятор Visual Basic подставляет данный предоставленный тип для каждого из вхождений `typename` в стандартном элементе.

- **Отсутствие ограничений.** Если вы не укажете все ограничения для параметра типа, код ограничивается операции и элементы, поддерживаемые [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) для этого параметра типа.

## <a name="example"></a>Пример

В следующем примере показано каркасное определение класса универсального словаря dictionary, включая каркас функции для добавления новой записи в словарь.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Пример

Поскольку `dictionary` является универсальным, использующий ее код можно создать различные объекты из него, каждый необходимости те же функциональные возможности, но выполняется на другой тип данных. В следующем примере показано строку кода, который создает `dictionary` со `String` записей и `Integer` ключи.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Пример

В следующем примере каркас определения, созданный в предыдущем примере.

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
