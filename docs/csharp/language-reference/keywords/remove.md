---
title: Справочник по C#. Контекстное ключевое слово remove
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 8ea3ea1910e28c03b2a894c64415cb2ccff942d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713148"
---
# <a name="remove-c-reference"></a>remove (Справочник по C#)

Контекстное ключевое слово `remove` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код отменяет подписку на [событие](event.md). Если указан настраиваемый метод доступа `remove`, также необходимо указать метод доступа [add](add.md).

## <a name="example"></a>Пример

В следующем примере показано событие с настраиваемыми методами доступа [add](add.md) и `remove`. Полный пример см. в статье [Как реализовать события интерфейса (руководство по программированию на C#)](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.

## <a name="see-also"></a>См. также раздел

- [События](../../programming-guide/events/index.md)
