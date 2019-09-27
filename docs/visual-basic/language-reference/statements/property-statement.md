---
title: Оператор Property (Visual Basic)
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
ms.openlocfilehash: 2c3e417aad404171a43342dc92773615ec350ef5
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332750"
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

  Необязательный параметр. Список атрибутов, применяемых к этому свойству, или `Get` или `Set` процедура. См. [список атрибутов](attribute-list.md).

- `Default`

  Необязательный параметр. Указывает, что это свойство является свойством по умолчанию для класса или структуры, в которой он определен. Свойства по умолчанию должны принимать параметры и могут быть заданы и получены без указания имени свойства. Если вы объявили свойство как `Default`, нельзя использовать `Private` в свойстве или в любой из его процедур свойств.

- `accessmodifier`

  Необязательно для оператора `Property` и не более чем в одном из операторов `Get` и `Set`. Ниже указаны доступные значения.

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Закрытые](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Private Protected](../modifiers/private-protected.md)

  См. раздел [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `propertymodifiers`

  Необязательный параметр. Ниже указаны доступные значения.

  - [Перегрузки](../modifiers/overloads.md)

  - [Переопределения](../modifiers/overrides.md)

  - [Переопределяемые](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Необязательный параметр. См. раздел [Shared](../modifiers/shared.md).

- `Shadows`

  Необязательный параметр. См. раздел [Shadows](../modifiers/shadows.md).

- `ReadOnly`

  Необязательный параметр. См. раздел [ReadOnly](../modifiers/readonly.md).

- `WriteOnly`

  Необязательный параметр. См. раздел [WriteOnly](../modifiers/writeonly.md).

- `Iterator`

  Необязательный параметр. См. [итератор](../modifiers/iterator.md).

- `name`

  Обязательный. Имя свойства. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `parameterlist`

  Необязательный параметр. Список имен локальных переменных, представляющих параметры этого свойства, и возможные дополнительные параметры процедуры `Set`. См. [список параметров](parameter-list.md).

- `returntype`

  Требуется, если `Option Strict` имеет значение `On`. Тип данных значения, возвращаемого этим свойством.

- `Implements`

  Необязательный параметр. Указывает, что это свойство реализует одно или несколько свойств, каждое из которых определено в интерфейсе, реализуемом классом или структурой этого свойства. См. [инструкцию Implements](implements-statement.md).

- `implementslist`

  Является обязательным, если предоставлен параметр `Implements`. Список реализуемых свойств.

  `implementedproperty [ , implementedproperty ... ]`

  Каждый элемент `implementedproperty` имеет перечисленные ниже синтаксис и компоненты.

  `interface.definedname`

  |Отделение|Описание|
  |---|---|
  |`interface`|Обязательный. Имя интерфейса, реализованного в классе или структуре этого свойства.|
  |`definedname`|Обязательный. Имя, по которому определяется свойство в `interface`.|

- `Get`

  Необязательный параметр. Требуется, если свойство помечено как `ReadOnly`. Запускает процедуру свойства `Get`, которая используется для возврата значения свойства.  Инструкция `Get` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `statements`

  Необязательный параметр. Блок инструкций для выполнения в процедуре `Get` или `Set`.

- `End Get`

  Завершает процедуру свойства `Get`.

- `Set`

  Необязательный параметр. Требуется, если свойство помечено как `WriteOnly`. Запускает процедуру свойства `Set`, используемую для хранения значения свойства.  Инструкция `Set` не используется с [автоматической реализацией свойств](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

- `End Set`

  Завершает процедуру свойства `Set`.

- `End Property`

  Завершает определение этого свойства.

## <a name="remarks"></a>Примечания

Оператор `Property` вводит объявление свойства. Свойство может иметь процедуру `Get` (только для чтения), процедуру `Set` (только для записи) или и то, и другое (чтение и запись). При использовании автоматического реализуемого свойства можно опустить процедуру `Get` и `Set`. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../programming-guide/language-features/procedures/auto-implemented-properties.md).

@No__t-0 можно использовать только на уровне класса. Это означает, что *контекст объявления* для свойства должен быть классом, структурой, модулем или интерфейсом и не может быть исходным файлом, пространством имен, процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).

По умолчанию свойства используют общий доступ. Уровень доступа свойства можно настроить с помощью модификатора доступа в операторе `Property`. при необходимости можно изменить одну из процедур свойств на более ограниченный уровень доступа.

Visual Basic передает параметр в процедуру `Set` во время назначения свойств. Если параметр для `Set` не указан, в интегрированной среде разработки (IDE) используется неявный параметр с именем `value`. Этот параметр содержит значение, присваиваемое свойству. Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом вызове процедуры `Get`.

## <a name="rules"></a>Правила

- **Уровни смешанного доступа.** При определении свойства для чтения и записи можно дополнительно указать другой уровень доступа для `Get` или `Set`, но не для обоих. В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства. Например, если свойство объявлено `Friend`, можно объявить процедуру `Set` `Private`, но не `Public`.

  Если вы определяете свойство `ReadOnly` или `WriteOnly`, то процедура с одним свойством (`Get` или `Set` соответственно) представляет все свойство. Для такой процедуры нельзя объявить другой уровень доступа, поскольку в этом случае для свойства будет задано два уровня доступа.

- **Тип возвращаемого значения.** Оператор `Property` может объявлять тип данных возвращаемого значения. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса.

  Если не указать `returntype`, свойство возвращает значение `Object`.

- **Реализации.** Если в этом свойстве используется ключевое слово `Implements`, содержащий класс или структуру должны содержать оператор `Implements` сразу после оператора `Class` или `Structure`. Оператор `Implements` должен содержать каждый интерфейс, указанный в `implementslist`. Однако имя, по которому интерфейс определяет `Property` (в `definedname`), не обязательно должно совпадать с именем этого свойства (в `name`).

## <a name="behavior"></a>Поведение

- **Возврат из процедуры свойства.** Когда процедура `Get` или `Set` возвращает в вызывающий код, выполнение продолжится с оператора, следующего за оператором, вызвавшим ее.

  Операторы `Exit Property` и `Return` вызывают немедленный выход из процедуры свойства. Любое число инструкций `Exit Property` и `Return` может использоваться в любом месте процедуры, и можно сочетать операторы `Exit Property` и `Return`.

- **Возвращаемое значение.** Чтобы вернуть значение из процедуры `Get`, можно либо присвоить значение имени свойства, либо включить его в инструкцию `Return`. В следующем примере возвращаемое значение присваивается имени свойства `quoteForTheDay`, а затем используется инструкция `Exit Property` для возврата.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  Если вы используете `Exit Property` без присвоения значения `name`, процедура `Get` Возвращает значение по умолчанию для типа данных свойства.

  В то же время инструкция `Return` назначает возвращаемое значение процедуры `Get` и завершает процедуру. Это показано в следующем примере.

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
