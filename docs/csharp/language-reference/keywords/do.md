---
title: Справочник по C#. do
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 08f964b1e5c78a429dc50f81398d840f58ec4b13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422837"
---
# <a name="do-c-reference"></a>do (Справочник по C#)

Оператор `do` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`. Так как это выражение оценивается после каждого выполнения цикла, цикл `do-while` выполняется один или несколько раз. Это отличает его от цикла [while](while.md), который выполняется от нуля до нескольких раз.

В любой точке блока операторов `do` можно разорвать цикл с помощью оператора [break](break.md).

Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md). Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла. В противном случае выполнение продолжается с первого оператора после цикла.

Также можно выйти из цикла `do-while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

## <a name="example"></a>Пример

В следующем примере показано применение оператора `do`. Нажмите **Запустить** для выполнения примера кода. После этого можно изменить код и запустить его еще раз.

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор do](~/_csharplang/spec/statements.md#the-do-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Оператор while](while.md)
