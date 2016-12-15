---
title: "Практическое руководство. Запрос коллекции объектов (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "запрос коллекции объектов [C#]"
  - "запросы [LINQ в C#], коллекции объектов"
  - "выражения запросов [LINQ в C#], коллекции объектов"
ms.assetid: 122d1e3b-1604-4add-b6b4-b84530a77b6b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Запрос коллекции объектов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующем примере показано, как выполнить простой запрос через список объектов `Student`.  Каждый объект `Student` содержит некоторую базовую информацию об учащемся и список, представляющий баллы учащегося по четырем экзаменам.  
  
 Это приложение служит в качестве основы для многих других примеров в этом разделе, использующих общий источник данных  `students` .  
  
## Пример  
 Следующий запрос возвращает список учащихся, получивших на первом экзамене балл 90 или выше.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-query-a-collection-of-objects_1.cs)]  
  
 Этот запрос специально сделан простым, чтобы позволить поэкспериментировать с ним.  Например, можно попробовать дополнительные предикаты в предложении `where` воспользоваться предложением `orderby` для сортировки результатов.  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)], предназначенный для платформы .NET Framework версии 3.5.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Скопируйте код в созданный проект.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)