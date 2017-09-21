---
title: "remove (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remove_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b34d653a40e1309e281235416c0399abc6dd9a0d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="remove-c-reference"></a>remove (Справочник по C#)
Контекстное ключевое слово `remove` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код отменяет подписку на [событие](../../../csharp/language-reference/keywords/event.md). Если указан настраиваемый метод доступа `remove`, также необходимо указать метод доступа [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано событие с настраиваемыми методами доступа [add](../../../csharp/language-reference/keywords/add.md) и `remove`. Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также  
 [События](../../../csharp/programming-guide/events/index.md)

