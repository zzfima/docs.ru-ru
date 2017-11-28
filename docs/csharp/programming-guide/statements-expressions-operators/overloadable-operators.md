---
title: "Перегружаемые операторы (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 92dde781aa258267b7140228bc87621d26713f6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="overloadable-operators-c-programming-guide"></a>Перегружаемые операторы (Руководство по программированию в C#)

C# позволяет пользовательским типам перегружать операторы путем определения статических функций-членов с помощью ключевого слова [operator](../../../csharp/language-reference/keywords/operator.md). Не все операторы могут быть перегружены; кроме того, некоторые операторы имеют ограничения, как указано в следующей таблице.

| Операторы | Возможность перегрузки |
| --------- | --------------- |
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [!](../../../csharp/language-reference/operators/logical-negation-operator.md), [~](../../../csharp/language-reference/operators/bitwise-complement-operator.md), [++](../../../csharp/language-reference/operators/increment-operator.md), [--](../../../csharp/language-reference/operators/decrement-operator.md), [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md)|Эти унарные операторы могут быть перегружены.|
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md), [%](../../../csharp/language-reference/operators/modulus-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md), [^](../../../csharp/language-reference/operators/xor-operator.md), [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md), [>>](../../../csharp/language-reference/operators/right-shift-operator.md)|Эти бинарные операторы могут быть перегружены.|
|[==](../../../csharp/language-reference/operators/equality-comparison-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [\<](../../../csharp/language-reference/operators/less-than-operator.md), [>](../../../csharp/language-reference/operators/greater-than-operator.md), [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md), [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|Операторы сравнения могут быть перегружены (но см. примечание после этой таблицы).|
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|Условные логические операторы не могут быть перегружены, но они оцениваются с помощью `&` и <code>&#124;</code>, которые могут быть перегружены.|
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|Оператор индексирования массива не может быть перегружен, но можно определить индексаторы.|
|[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)|Оператор приведения типов не может быть перегружен, но можно определить новые операторы преобразования (см. [explicit](../../../csharp/language-reference/keywords/explicit.md) и [implicit](../../../csharp/language-reference/keywords/implicit.md)).|
|[+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [\*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [\<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|Операторы присваивания не могут быть перегружены, но `+=`, например, оценивается с помощью `+`, который может быть перегружен.|
|[=](../../../csharp/language-reference/operators/assignment-operator.md), [.](../../../csharp/language-reference/operators/member-access-operator.md), [?:](../../../csharp/language-reference/operators/conditional-operator.md), [??](../../../csharp/language-reference/operators/null-conditional-operator.md), [->](../../../csharp/language-reference/operators/dereference-operator.md), [=>](../../../csharp/language-reference/operators/lambda-operator.md), [f(x)](../../../csharp/language-reference/operators/invocation-operator.md), [as](../../../csharp/language-reference/keywords/as.md), [checked](../../../csharp/language-reference/keywords/checked.md), [unchecked](../../../csharp/language-reference/keywords/unchecked.md), [default](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../../csharp/language-reference/keywords/is.md), [new](../../../csharp/language-reference/keywords/new.md), [sizeof](../../../csharp/language-reference/keywords/sizeof.md), [typeof](../../../csharp/language-reference/keywords/typeof.md)|Эти операторы не могут быть перегружены.|

> [!NOTE]
> При перегрузке операторов сравнения они должны перегружаться парами; то есть если оператор `==` перегружается, оператор `!=` тоже должен перегружаться. Обратное также верно, если для перегрузки оператора `!=` требуется перегрузка оператора `==`. То же справедливо для операторов сравнения `<` и `>`, а также `<=` и `>=`.

Для перегрузки оператора в пользовательском классе нужно создать метод в этом классе с правильной сигнатурой. Метод должен иметь имя «operator X», где X — имя или символ оператора для перегрузки. Унарные операторы имеют один параметр, а бинарные операторы имеют два параметра. В каждом случае один параметр должен быть того же типа, что и объявляющий его класс или структура.

```csharp
public static Complex operator +(Complex c1, Complex c2)
{
    return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
}
```

Часто используются определения, которые просто немедленно возвращаются с результатом выражения.  Для таких ситуаций существует сокращенный синтаксис с использованием `=>`.

```csharp
public static Complex operator +(Complex c1, Complex c2) =>
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
  
// Override ToString() to display a complex number in the traditional format:
public override string ToString() => $"{this.real} + {this.imaginary}";
```

Дополнительные сведения см. в разделе [Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).

## <a name="see-also"></a>См. также

[Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
[Инструкции, выражения и операторы](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
[Операторы в C#](../../../csharp/language-reference/operators/index.md)  
[Почему перегруженные операторы всегда являются статическими в C#?](http://go.microsoft.com/fwlink/?LinkId=112383)
