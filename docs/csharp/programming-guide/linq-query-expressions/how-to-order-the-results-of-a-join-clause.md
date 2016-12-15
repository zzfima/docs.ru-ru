---
title: "Практическое руководство. Упорядочение результатов предложения соединения (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "join - предложение [C#]"
  - "соединения [C#], сортировка результатов"
  - "запросы [LINQ в C#], соединения"
  - "выражения запросов [LINQ в C#], соединения"
ms.assetid: 83f36f16-2ba3-453f-8b9f-7d02b415610e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Упорядочение результатов предложения соединения (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере показано, как упорядочить результаты операции соединения.  Обратите внимание, что упорядочение выполняется после соединения.  Хотя до выполнения соединения можно использовать предложение `orderby` с указанием одной или нескольких исходных последовательностей, это делать не рекомендуется.  Некоторые поставщики [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] могут не сохранять этот порядок после соединения.  
  
## Пример  
 Этот запрос создает группу соединения, а затем сортирует группы на основе элемента категории, который все еще находится в области действия.  Внутри анонимного инициализатора элементов вложенный запрос упорядочивает все соответствующие элементы из последовательности продуктов.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-order-the-results-of-a-join-clause_1.cs)]  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)], предназначенный для платформы .NET Framework версии 3.5.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Скопируйте код в созданный проект.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение orderby](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [Предложение join](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)