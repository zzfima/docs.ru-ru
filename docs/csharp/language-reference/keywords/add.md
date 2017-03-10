---
title: "add (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "add_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "add - метод доступа события [C#]"
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# add (Справочник по C#)
Контекстно\-зависимое ключевое слово `add` используется для определения пользовательского метода доступа к событию, вызываемому при подписке клиентского кода к [событию](../../../csharp/language-reference/keywords/event.md).  Если указан пользовательский метод доступа `add`, то необходимо также указать метод доступа [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## Пример  
 В следующем примере показано событие, имеющее пользовательские методы доступа `add` и [remove](../../../csharp/language-reference/keywords/remove.md).  Полный пример см. в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/csharp/add_1.cs)]  
  
 Обычно не требуется предоставлять свои собственные пользовательские методы доступа к событиям.  Для большинства сценариев достаточны методы доступа, которые автоматически создаются компилятором при объявлении события.  
  
## См. также  
 [События](../../../csharp/programming-guide/events/index.md)