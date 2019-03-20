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
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="5753b-102">Руководство по программированию на C#. Использование словаря для хранения экземпляров событий</span><span class="sxs-lookup"><span data-stu-id="5753b-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="5753b-103">Вы можете применять пользовательские методы доступа `add` и `remove` для предоставления большого числа событий, чтобы вместо отдельного поля для каждого события использовался экземпляр <xref:System.Collections.Generic.Dictionary%602> для хранения экземпляров событий, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="5753b-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="5753b-104">Такой подход эффективен, только если у вас будет большое число событий, на которые вы не будете подписаны.</span><span class="sxs-lookup"><span data-stu-id="5753b-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="5753b-105">Эта реализация соответствует поведению [добавления и удаления делегатов](~/_csharplang/spec/delegates.md#delegate-invocation) в спецификации языка C#.</span><span class="sxs-lookup"><span data-stu-id="5753b-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="5753b-106">Обратите внимание, что оператор [lock](../../language-reference/keywords/lock-statement.md) применяется только для *доступа* к словарю с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="5753b-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="5753b-107">Не вызывайте обработчик событий в самом операторе `lock`, так как это может привести к взаимоблокировкам или конкуренции блокировок.</span><span class="sxs-lookup"><span data-stu-id="5753b-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="5753b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5753b-108">See also</span></span>

- [<span data-ttu-id="5753b-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5753b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5753b-110">События</span><span class="sxs-lookup"><span data-stu-id="5753b-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="5753b-111">Делегаты</span><span class="sxs-lookup"><span data-stu-id="5753b-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
