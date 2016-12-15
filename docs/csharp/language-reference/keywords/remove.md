---
title: "remove (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remove_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "remove - метод доступа события [C#]"
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# remove (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Контекстно\-зависимое ключевое слово `remove` используется для определения пользовательского метода доступа к событию, вызываемому при отмене подписки клиентского кода от [события](../../../csharp/language-reference/keywords/event.md).  Если указан пользовательский метод доступа `remove`, то необходимо также указать метод доступа [add](../../../csharp/language-reference/keywords/add.md).  
  
## Пример  
 В следующем примере показано событие с пользовательскими методами доступа [add](../../../csharp/language-reference/keywords/add.md) и `remove`.  Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Обычно не требуется предоставлять свои собственные пользовательские методы доступа к событиям.  Для большинства сценариев достаточны методы доступа, которые автоматически создаются компилятором при объявлении события.  
  
## См. также  
 [События](../../../csharp/programming-guide/events/index.md)