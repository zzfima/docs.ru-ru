---
title: Справочник по C#. if-else
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 98c1a8dceec3e5a47627841988e2d722c56fc36c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715263"
---
# <a name="if-else-c-reference"></a>if-else (Справочник по C#)

Оператор `if` определяет, какой оператор будет выполняться при выполнения условия, заданного логическим выражением. В приведенном ниже примере переменной `bool` типа `condition` присваивается значение `true` , а затем она проверяется оператором `if` . В результате получается `The variable is set to true.`.

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

Примеры в этом разделе можно выполнить, разместив их в методе `Main` консольного приложения.

Оператор `if` в С# может иметь две формы, как показано в приведенном ниже примере.

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

В операторе `if-else` , если `condition` имеет значение true, выполняется `then-statement` . Если `condition` имеет значение false, выполняется `else-statement` . Так как `condition` не может одновременно иметь значения true и false, `then-statement` и `else-statement` оператора `if-else` не могут выполняться оба. После выполнения `then-statement` или `else-statement` управление передается следующему оператору после оператора `if` .

В операторе `if` , не включающем оператор `else` , если `condition` имеет значение true, выполняется `then-statement` . Если `condition` имеет значение false, то управление передается следующему оператору после оператора `if` .

`then-statement` и `else-statement` могут состоять из одного или нескольких операторов, заключенных в фигурные скобки (`{}`). Для одного оператора скобки необязательны, но рекомендуются.

Оператор или операторы в `then-statement` и `else-statement` могут быть любого типа, включая другой оператор `if` , вложенный в исходный оператор `if` . Во вложенных операторах `if` каждое предложение `else` относится к последнему оператору `if` , у которого нет соответствующего объекта `else`. В приведенном ниже примере `Result1` получается, если оба выражения `m > 10` и `n > 20` имеют значение true. Если `m > 10` имеет значение true, но `n > 20` — значение false, то получается `Result2` .

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

Если вместо этого нужно, чтобы `Result2` получался, когда значение `(m > 10)` равно false, можно указать такую связь с помощью фигурных скобок для задания начала и конца вложенного оператора `if` , как показано в приведенном ниже примере.

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

`Result2` получается, если условие `(m > 10)` имеет значение false.

## <a name="example"></a>Пример

В приведенном ниже примере вы вводите символ с помощью клавиатуры, а программа использует вложенный оператор `if` для определения того, является ли введенный символ буквой. Если введенный символ является буквой, программа определяет его регистр. Для каждого случая предусмотрено отдельное сообщение.

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a>Пример

Также можно поместить оператор `if` в блок else, как показано в части кода, приведенной ниже. В примере операторы `if` помещаются в два блока else и один блок then. Комментарии определяют какие условия выполняются в каждом из блоков.

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a>Пример

В приведенном ниже примере определяется, является ли введенный символ строчной буквой, прописной буквой или цифрой. Если все три условия имеют значение false, то символ не является алфавитно-цифровым. Для каждого случая выводится сообщение.

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

Точно так же как оператор в блоке else или блоке then может быть любым допустимым оператором, в качестве условия можно использовать любое допустимое логическое выражение. Вы можете использовать [логические операторы](../operators/boolean-logical-operators.md), такие как `!`, `&&`, `||`, `&`, `|`и `^`, для формирования составных условий. В коде ниже приведены примеры.

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [?: Оператор](../operators/conditional-operator.md)
- [Оператор if-else (C++)](/cpp/cpp/if-else-statement-cpp)
- [switch](switch.md)
