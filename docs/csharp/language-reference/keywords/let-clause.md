---
title: Справочник по C#. Предложение let
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 941ad41d75e14420699022a07bd6a3b10d83c896
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243404"
---
# <a name="let-clause-c-reference"></a>Предложение let (справочник по C#)

В выражении запроса иногда требуется сохранить результат вложенного выражения, который будет использоваться в последующих предложениях. Это можно сделать с помощью ключевого слова `let`, которое создает новую переменную диапазона и инициализирует ее, используя результат предоставленного выражения. После инициализации с использованием этого значения такую переменную диапазона нельзя использовать для хранения других значений. Тем не менее если переменная диапазона хранит запрашиваемый тип, к ней можно выполнять запросы.

## <a name="example"></a>Пример

В следующем примере показываются два способа использования `let`:

1. Создание перечисляемого типа, к которому можно выполнять запросы.

2. Реализация запроса с однократным вызовом `ToLower` для переменной диапазона `word`. Если ключевое слово `let` не используется, потребуется выполнять вызов `ToLower` в каждом предикате предложения `where`.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../language-reference/index.md)
- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [LINQ](../../linq/index.md)
- [Приступая к работе с LINQ в C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [Обработка исключений в выражениях запросов](../../linq/handle-exceptions-in-query-expressions.md)