---
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346760"
---
# <a name="property-statement"></a>Property Statement

Объявляет имя свойства и процедуры свойства, используемые для хранения и извлечения значения свойства.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>Части

- `attributelist`

  Необязательно. Список атрибутов, применяемых к этому свойству, `Get` или `Set` процедуре. См. [список атрибутов](attribute-list.md).

- `Default`

  Необязательно. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой он определен. Свойства по умолчанию должны принимать параметры и могут быть заданы и получены без указания имени свойства. Если свойство объявляется как `Default`, нельзя использовать `Private` в свойстве или в любой из его процедур свойств.

- `accessmodifier`

  Необязательно для оператора `Property` и только для одной из `Get` и `Set` инструкций. Ниже указаны доступные значения.

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Закрытые](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Необязательно. Ниже указаны доступные значения.

  - [Overloads](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательно. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательно. См. раздел [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  Необязательно. См. раздел [ReadOnly](../modifiers/readonly.md).

- `WriteOnly`

  Необязательно. См. раздел [WriteOnly](../modifiers/writeonly.md).

- `Iterator`

  Необязательно. См. [итератор](../modifiers/iterator.md).

- `name`

  Обязательно. Имя свойства. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Необязательно. Список имен локальных переменных, представляющих параметры этого свойства, и возможные дополнительные параметры процедуры `Set`. См. [список параметров](parameter-list.md).

- `returntype`

  Требуется, если `Option Strict` `On`. Тип данных значения, возвращаемого этим свойством.

- `Implements`

  Необязательно. Указывает, что это свойство реализует одно или несколько свойств, каждое из которых определено в интерфейсе, реализуемом классом или структурой этого свойства. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.

  `implementedproperty [ , implementedproperty ... ]`

  Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательно. Имя интерфейса, реализованного в классе или структуре этого свойства.|
  |`definedname`|Обязательно. Имя, по которому свойство определяется в `interface`.|

- `Get`

  Необязательно. Требуется, если свойство помечено как `ReadOnly`. Запускает `Get` процедуру свойства, которая используется для возврата значения свойства.  Инструкция `Get` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  Необязательно. Блок инструкций для выполнения в рамках процедуры `Get` или `Set`.

- `End Get`

  Завершает процедуру свойства `Get`.

- `Set`

  Необязательно. Требуется, если свойство помечено как `WriteOnly`. Запускает `Set` процедуру свойства, используемую для хранения значения свойства.  Инструкция `Set` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Завершает процедуру свойства `Set`.

- `End Property`

  Завершает определение этого свойства.

## <a name="remarks"></a>Заметки

Оператор `Property` вводит объявление свойства. Свойство может иметь `Get`ую процедуру (только для чтения), `Set`ую процедуру (только запись) или и то, и другое (чтение и запись). При использовании автоматического реализуемого свойства можно опустить `Get` и `Set` процедуру. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

`Property` можно использовать только на уровне класса. Это означает, что *контекст объявления* для свойства должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

По умолчанию свойства используют общий доступ. Уровень доступа свойства можно настроить с помощью модификатора доступа в операторе `Property`. при необходимости можно изменить одну из процедур свойств на более ограниченный уровень доступа.

Visual Basic передает параметр в процедуру `Set` во время назначения свойств. Если параметр для `Set`не указан, в интегрированной среде разработки (IDE) используется неявный параметр с именем `value`. Этот параметр содержит значение, присваиваемое свойству. Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.

## <a name="rules"></a>Правила

- **Уровни смешанного доступа.** Если вы определяете свойство для чтения и записи, при необходимости можно указать другой уровень доступа либо для `Get`, либо для `Set` процедуры, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить `Set` процедуру `Private`, но не `Public`.

  Если вы определяете свойство `ReadOnly` или `WriteOnly`, то процедура с одним свойством (`Get` или `Set`соответственно) представляет все свойство. Для такой процедуры нельзя объявить другой уровень доступа, поскольку в этом случае для свойства будет задано два уровня доступа.

- **Тип возвращаемого значения.** Оператор `Property` может объявлять тип данных возвращаемого значения. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.

  Если не указать `returntype`, свойство возвращает `Object`.

- **Реализации.** Если в этом свойстве используется ключевое слово `Implements`, содержащий класс или структуру должны содержать инструкцию `Implements`, непосредственно следующую за инструкцией `Class` или `Structure`. Оператор `Implements` должен содержать каждый интерфейс, указанный в `implementslist`. Однако имя, по которому интерфейс определяет `Property` (в `definedname`) не обязательно должно совпадать с именем этого свойства (в `name`).

## <a name="behavior"></a>Поведение

- **Возврат из процедуры свойства.** Когда процедура `Get` или `Set` возвращается в вызывающий код, выполнение продолжится с оператора, следующего за оператором, вызвавшим ее.

  Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства. Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` и `Return` операторы.

- **Возвращаемое значение.** Чтобы вернуть значение из `Get` процедуры, можно либо присвоить значение имени свойства, либо включить его в инструкцию `Return`. В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay` а затем используется инструкция `Exit Property` для возврата.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Если вы используете `Exit Property` без присвоения значения `name`, процедура `Get` возвращает значение по умолчанию для типа данных свойства.

  Оператор `Return` в то же время присваивает возвращаемое значение процедуры `Get` и завершает процедуру. Это показано в следующем примере.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>Пример

В следующем примере объявляется свойство в классе.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>См. также

- [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Оператор Get](get-statement.md)
- [Оператор Set](set-statement.md)
- [Список параметров](parameter-list.md)
- [Default](../modifiers/default.md)
