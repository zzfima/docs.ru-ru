---
title: Руководство по программированию на C#. Использование словаря для хранения экземпляров событий
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845282"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Руководство по программированию на C#. Использование словаря для хранения экземпляров событий

Вы можете применять пользовательские методы доступа `add` и `remove` для предоставления большого числа событий, чтобы вместо отдельного поля для каждого события использовался экземпляр <xref:System.Collections.Generic.Dictionary%602> для хранения экземпляров событий, как показано в примере ниже. Такой подход эффективен, только если у вас будет большое число событий, на которые вы не будете подписаны.

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

Эта реализация соответствует поведению [добавления и удаления делегатов](~/_csharplang/spec/delegates.md#delegate-invocation) в спецификации языка C#.

Обратите внимание, что оператор [lock](../../language-reference/keywords/lock-statement.md) применяется только для *доступа* к словарю с обработчиками событий. Не вызывайте обработчик событий в самом операторе `lock`, так как это может привести к взаимоблокировкам или конкуренции блокировок.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [События](../../../csharp/programming-guide/events/index.md)
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
