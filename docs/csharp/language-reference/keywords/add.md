---
title: add (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: c1fa8c130475a67ac175205fe3491a32654ea475
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216032"
---
# <a name="add-c-reference"></a>add (Справочник по C#)
Контекстное ключевое слово `add` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код подписывается на [событие](../../../csharp/language-reference/keywords/event.md). Если указан настраиваемый метод доступа `add`, также необходимо указать метод доступа [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано событие с настраиваемыми методами доступа `add` и [remove](../../../csharp/language-reference/keywords/remove.md). Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также  
 [События](../../../csharp/programming-guide/events/index.md)
