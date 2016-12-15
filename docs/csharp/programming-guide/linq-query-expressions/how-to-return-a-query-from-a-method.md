---
title: "Практическое руководство. Возврат запроса из метода (Руководство по программированию на C#) | Microsoft Docs"
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
  - "метод возвращает запрос [C#]"
  - "запросы [LINQ в C#], метод возвращает запрос"
  - "выражения запросов [LINQ в C#], метод возвращает запрос"
ms.assetid: 9d6f20a7-f085-44cf-9df3-71948255ec68
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Возврат запроса из метода (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В данном примере показан способ возврата запроса из метода в качестве возвращаемого значения и параметра `out`.  
  
 Запрос должен иметь тип <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> или наследуемый тип, например <xref:System.Linq.IQueryable%601>.  Поэтому любое возвращаемое значение или параметр `out` метода, возвращающего запрос, должны также иметь этот тип.  Если метод материализует запрос в устойчивый тип <xref:System.Collections.Generic.List%601> или <xref:System.Array>, считается, что он должен возвращать результаты запроса, а не сам запрос.  Переменную запроса, возвращаемую из метода, можно формировать или изменять.  
  
## Пример  
 В следующем примере первый метод возвращает запрос в качестве возвращаемого значения, второй метод возвращает запрос в качестве параметра `out`.  Обратите внимание, что в обоих случаях возвращается запрос, а не его результаты.  
  
 [!code-cs[csProgGuideLINQ#80](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-a-query-from-a-method_1.cs)]  
  
## Компиляция кода  
  
-   Создайте проект [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)], предназначенный для платформы .NET Framework версии 3.5 или более поздней.  По умолчанию в проекте имеются ссылка на файл System.Core.dll и директива `using` \(C\#\) для пространства имен System.Linq.  
  
-   Замените класс с кодом в примере.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить программу.  
  
-   Нажмите любую клавишу для выхода из окна консоли.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)