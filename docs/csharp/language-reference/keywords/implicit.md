---
title: implicit. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 00fe1a02b52ef2ddc393bc7424efa73fc4059a9c
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610115"
---
# <a name="implicit-c-reference"></a>implicit (Справочник по C#)

Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа. Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.

## <a name="example"></a>Пример

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода. Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты. В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать. Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`. Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [explicit](explicit.md)
- [Перегрузка операторов](../operators/operator-overloading.md)
- [Практическое руководство. Реализация определяемых пользователем преобразований между структурами](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
