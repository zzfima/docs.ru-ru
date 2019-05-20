---
title: Справочник по C#. Контекстное ключевое слово remove
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: b5c604cbb0fef158750b0fa487374ab293795fc7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633721"
---
# <a name="remove-c-reference"></a>remove (Справочник по C#)

Контекстное ключевое слово `remove` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код отменяет подписку на [событие](event.md). Если указан настраиваемый метод доступа `remove`, также необходимо указать метод доступа [add](add.md).

## <a name="example"></a>Пример

В следующем примере показано событие с настраиваемыми методами доступа [add](add.md) и `remove`. Полный пример см. в [практическом руководстве по  реализации событий интерфейса](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.

## <a name="see-also"></a>См. также

- [События](../../programming-guide/events/index.md)
