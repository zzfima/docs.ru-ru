---
title: Оператор continue (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6a409fe8c7fd07342138eac11bfd1766014da1bd
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948359"
---
# <a name="continue-c-reference"></a>continue (Справочник по C#)

Оператор `continue` передает управление следующей итерации вложенного оператора [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) или [foreach](../../../csharp/language-reference/keywords/foreach-in.md), в котором она встречается.

## <a name="example"></a>Пример

В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10. Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

[Справочник по C#](../../../csharp/language-reference/index.md)  
[Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
[Оператор break](/cpp/cpp/break-statement-cpp)  
[Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)