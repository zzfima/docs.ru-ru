---
title: Ключевое слово explicit (справочник по C#)
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 3567a2c5aa549aa3141ed59c3e93e7b07975da70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43463147"
---
# <a name="explicit-c-reference"></a>explicit (Справочник по C#)

Ключевое слово `explicit` объявляет оператор преобразования определяемого пользователем типа, который должен быть вызван с помощью приведения.

В следующем примере определяется оператор, который преобразует класс `Fahrenheit` в класс `Celsius`. Оператор должен быть определен в классе `Fahrenheit` или в классе `Celsius`:

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

Вызовите определенный оператор преобразования с помощью приведения, как показано в следующем примере:

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

Оператор преобразования преобразует исходный тип в конечный. Исходный тип предоставляет оператор преобразования. В отличие от неявного преобразования, операторы явного преобразования должны вызываться с помощью приведения. Если операция преобразования может вызвать исключения или привести к потере данных, следует пометить ее как `explicit`. Это предотвращает выполнение компилятором скрытого вызова операции преобразования с возможно непредвиденными последствиями.

Пропуск приведения приводит к ошибке времени компиляции CS0266.

Дополнительные сведения см. в разделе [Использование операторов преобразования](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="example"></a>Пример

В следующем примере приводятся классы `Fahrenheit` и `Celsius`, каждый из которых предоставляет явный оператор преобразования в другой класс.

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a>Пример

В следующем примере определяется структура `Digit`, представляющая одну десятичную цифру. Оператор определен для преобразования из `byte` в `Digit`, но поскольку не все байты могут быть преобразованы в `Digit`, выполняется явное преобразование.

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)  
- [Руководство по программированию на C#](../../programming-guide/index.md)  
- [Ключевые слова в C#](index.md)  
- [implicit](implicit.md)  
- [operator (справочник по C#)](operator.md)  
- [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
- [Связанные пользовательские явные преобразования в C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)  
