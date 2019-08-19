---
title: Операторы доступа к членам. Справочник по C#
description: Дополнительные сведения об операторах C#, которые можно использовать для доступа к членам типа.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 763fdb442fa0037dafd51f89badd04436e24d254
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566831"
---
# <a name="member-access-operators-c-reference"></a>Операторы доступа к членам (справочник по C#)

При доступе к члену типа можно использовать следующие операторы:

- [`.` (доступ к члену) ](#member-access-operator-): для доступа к члену пространства имен или типа;
- [`[]` (элемент массива или индексатор доступа) ](#indexer-operator-): для доступа к элементу массива или индексатору типа;
- [`?.` и `?[]` (null-условные операторы)](#null-conditional-operators--and-): для выполнения операции доступа члена или элемента только в том случае, если операнд не равен null;
- [`()` (вызов) ](#invocation-operator-): для вызова метода или делегата.

## <a name="member-access-operator-"></a>Оператор доступа к элементу .

Маркер `.` используется для обращения к члену пространства имен или типа, как в следующих примерах.

- Используйте `.` для обращения к пространству имен, вложенному в другое пространство имен, как показано в следующем примере [директивы `using`](../keywords/using-directive.md).

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- Используйте `.` для создания *полного имени* для обращения к типу в пределах пространства имен, как показано в следующем коде:

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  Используйте [директиву `using`](../keywords/using-directive.md), чтобы сделать использование полных имен необязательным.

- Используйте `.` для обращения к [членам типов](../../programming-guide/classes-and-structs/index.md#members) (статическим и нестатическим), как показано в следующем коде:

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

Можно также использовать `.` для вызова [метода расширения](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="indexer-operator-"></a>Оператор индексатора []

Квадратные скобки, `[]`, обычно используются для доступа к элементам массива, индексатора или указателя.

### <a name="array-access"></a>Доступ к массиву

В приведенном ниже примере показано, как получить доступ к элементам массива.

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

Если индекс массива выходит за границы соответствующего измерения массива, возникает исключение <xref:System.IndexOutOfRangeException>.

Как показано в предыдущем примере, квадратные скобки также используются в объявлении типа массива и для создания экземпляров массива.

Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Доступ к индексатору

В приведенном ниже примере используется тип .NET <xref:System.Collections.Generic.Dictionary%602> для демонстрации доступа к индексатору.

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

Индексаторы позволяют индексировать экземпляры определяемого пользователем типа аналогично индексации массива. В отличие от индексов массива, которые должны быть целым числом, аргументы индексатора могут быть объявлены любым типом.

Дополнительные сведения см. в [руководстве по работе с индексаторами](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Другие данные об использовании []

Сведения о доступе к элементу указателя см. в разделе, посвященном [оператору доступа к элементу указателя []](pointer-related-operators.md#pointer-element-access-operator-), статьи [Операторы, связанные с указателем](pointer-related-operators.md).

Кроме того, с помощью квадратных скобок можно указывать [атрибуты](../../programming-guide/concepts/attributes/index.md).

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>NULL-условные операторы: ?. и ?[]

В C# 6 и более поздних версий доступен null-условный оператор доступа к членам, `?.`, или доступа к элементам, `?[]`, который дает доступ к операнду только в том случае, если он имеет значение, отличное от NULL. Если операнд имеет значение `null`, результатом применения оператора является `null`. Null-условный оператор доступа к элементу `?.` также называется элвис-оператором.

Операторы с условием NULL предусматривают сокращенную обработку. То есть, если в цепочке операций условного доступа к элементу или члену одна из операций возвращает значение `null`, остальная цепочка не выполняется. В следующем примере `B` не вычисляется, если `A` принимает значение `null`, и `C` не вычисляется, если `A` или `B` принимает значение `null`.

```csharp
A?.B?.Do(C);
A?.B?[C];
```

В следующем примере иллюстрируется использование операторов `?.` и `?[]`.

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

В предыдущем примере также показано использование [оператора объединения с null](null-coalescing-operator.md). Можно использовать оператор объединения с null, чтобы задать альтернативное выражение для оценки на случай, если результат null-условной операции будет равен `null`.

### <a name="thread-safe-delegate-invocation"></a>Потокобезопасный вызов делегата

Используйте оператор `?.` для проверки того, что делегат не равен null, и его вызова потокобезопасным способом (например, в том случае, когда вы собираетесь [породить событие](../../../standard/events/how-to-raise-and-consume-events.md)), как показано в следующем коде:

```csharp
PropertyChanged?.Invoke(…)
```

Этот код эквивалентен следующему коду, который будет использоваться в C# 5 или более ранней версии:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a>Оператор вызова ()

Используйте скобки, `()`, чтобы вызвать [метод](../../programming-guide/classes-and-structs/methods.md) или [делегат](../../programming-guide/delegates/index.md).

Приведенный ниже пример демонстрирует вызов делегата и метода с аргументами или без них.

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

Круглые скобки также можно использовать при вызове [конструктора](../../programming-guide/classes-and-structs/constructors.md) с оператором [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Другие данные об использовании ()

Кроме того, с помощью круглых скобок можно указывать порядок выполнения операций в выражении. Дополнительные сведения см. в разделе [Добавление скобок](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) руководства по использованию [операторов](../../programming-guide/statements-expressions-operators/operators.md). Список операторов, упорядоченных по уровню приоритета, см. в статье [Операторы в C#](index.md).

В [выражениях приведения](type-testing-and-cast.md#cast-operator-), которые выполняют явные преобразования типов, также используйте круглые скобки.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Операторы `.` и `()` не могут быть перегружены. Оператор `[]` также считается неперегружаемым. Используйте [индексаторы](../../programming-guide/indexers/index.md) для поддержки индексирования с помощью определяемых пользователем типов.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Доступ к членам](~/_csharplang/spec/expressions.md#member-access)
- [Доступ к элементам](~/_csharplang/spec/expressions.md#element-access)
- [Null-условный оператор](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Выражения вызова](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Оператор ?? (оператор объединения со значением NULL)](null-coalescing-operator.md)
- [Оператор ::](namespace-alias-qualifier.md)
