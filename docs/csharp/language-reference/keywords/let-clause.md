---
title: Справочник по C#. Предложение let
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3ce2b663e5678de6b53db610b489f85ab1427b9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173592"
---
# <a name="let-clause-c-reference"></a>Предложение let (справочник по C#)

В выражении запроса иногда требуется сохранить результат вложенного выражения, который будет использоваться в последующих предложениях. Это можно сделать с помощью ключевого слова `let`, которое создает новую переменную диапазона и инициализирует ее, используя результат предоставленного выражения. После инициализации с использованием этого значения такую переменную диапазона нельзя использовать для хранения других значений. Тем не менее если переменная диапазона хранит запрашиваемый тип, к ней можно выполнять запросы.

## <a name="example"></a>Пример

В следующем примере показываются два способа использования `let`:

1. Создание перечисляемого типа, к которому можно выполнять запросы.

2. Реализация запроса с однократным вызовом `ToLower` для переменной диапазона `word`. Если ключевое слово `let` не используется, потребуется выполнять вызов `ToLower` в каждом предикате предложения `where`.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../../language-reference/index.md)
- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [LINQ в C#](../../linq/index.md)
- [LINQ](../../programming-guide/concepts/linq/index.md)
- [Обработка исключений в выражениях запросов](../../linq/handle-exceptions-in-query-expressions.md)
