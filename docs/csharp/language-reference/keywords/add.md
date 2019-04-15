---
title: Справочник по C#. Ключевое слово add
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 1f699e5729354d13bfbe29810bf2c4baf91d2382
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147918"
---
# <a name="add-c-reference"></a>add (Справочник по C#)
Контекстное ключевое слово `add` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код подписывается на [событие](../../../csharp/language-reference/keywords/event.md). Если указан настраиваемый метод доступа `add`, также необходимо указать метод доступа [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано событие с настраиваемыми методами доступа `add` и [remove](../../../csharp/language-reference/keywords/remove.md). Полный пример см. в [практическом руководстве по  реализации событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также

- [События](../../../csharp/programming-guide/events/index.md)
