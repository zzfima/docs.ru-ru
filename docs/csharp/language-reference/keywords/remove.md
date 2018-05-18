---
title: remove (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 16a169ce1a0ef5dbc29739b2d808acb19737669e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="remove-c-reference"></a>remove (Справочник по C#)
Контекстное ключевое слово `remove` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код отменяет подписку на [событие](../../../csharp/language-reference/keywords/event.md). Если указан настраиваемый метод доступа `remove`, также необходимо указать метод доступа [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано событие с настраиваемыми методами доступа [add](../../../csharp/language-reference/keywords/add.md) и `remove`. Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также  
 [События](../../../csharp/programming-guide/events/index.md)
