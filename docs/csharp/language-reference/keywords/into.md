---
title: into. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: ccb1463db51510d275b7053955a0257bd4fe621e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422713"
---
# <a name="into-c-reference"></a>into (Справочник по C#)

Контекстное слово `into` можно использовать для создания временного идентификатора для сохранения результатов предложений [group](group-clause.md), [join](join-clause.md) или [select](select-clause.md) в новый идентификатор. Этот идентификатор может сам по себе стать источником дополнительных команд запроса. При использовании в предложениях `group` или `select` применение нового идентификатора может называться *продолжением*.

## <a name="example"></a>Пример

В следующем примере показано использование ключевого слова `into` для создания временного идентификатора `fruitGroup`, который имеет выведенный тип `IGrouping`. С помощью идентификатора можно вызвать метод <xref:System.Linq.Enumerable.Count%2A> для каждой группы и выбрать только те группы, которые содержат несколько слов.

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

Использование ключевого слова `into` в предложении `group` необходимо только в тех случаях, когда требуется выполнить дополнительные операции запроса для каждой группы. Дополнительные сведения см. в разделе [Предложение group](group-clause.md).

Пример использования ключевого слова `into` в предложении `join` см. в разделе [Предложение join](join-clause.md).

## <a name="see-also"></a>См. также

- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [LINQ в C#](../../linq/index.md)
- [предложение group](group-clause.md)
