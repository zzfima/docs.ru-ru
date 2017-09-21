---
title: "add (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- add_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
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
ms.openlocfilehash: 0171cbb28c7d32cb4f8cad6bd46cd9aeda10fccc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="add-c-reference"></a>add (Справочник по C#)
Контекстное ключевое слово `add` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код подписывается на [событие](../../../csharp/language-reference/keywords/event.md). Если указан настраиваемый метод доступа `add`, также необходимо указать метод доступа [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано событие с настраиваемыми методами доступа `add` и [remove](../../../csharp/language-reference/keywords/remove.md). Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также  
 [События](../../../csharp/programming-guide/events/index.md)

