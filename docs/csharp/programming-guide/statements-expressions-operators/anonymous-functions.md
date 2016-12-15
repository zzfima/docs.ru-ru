---
title: "Анонимные функции (Руководство по программированию на C#) | Microsoft Docs"
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
  - "анонимные функции [C#]"
  - "анонимные методы [C#]"
  - "лямбда-выражения [C#], в качестве анонимных функций"
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Анонимные функции (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Анонимная функция – это оператор или выражение "inline", которое можно использовать каждый раз, когда ожидается тип делегата.  Ее можно использовать для инициализации именованного делегата или подставить вместо типа именованного делегата в качестве параметра метода.  
  
 Существует два типа анонимных функций, каждый из которых по отдельности рассматривается в следующих разделах:  
  
-   [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Лямбда\-выражения можно привязать к деревьям выражений и к делегатам.  
  
## Эволюция делегатов в C\#  
 В языке C\# 1.0 разработчик создавал экземпляр делегата путем его явной инициализации с методом, определенным в каком\-либо месте кода.  В C\# версии 2.0 представлена концепция анонимных методов, которые позволяют писать блоки неименованных встраиваемых выражений, которые можно выполнять в вызове делегата.  В языке C\# версии 3.0 представлены лямбда\-выражения, сходные с анонимным методам, но более выразительные и лаконичные.  Две эти возможности вместе называются *анонимными функциями*.  В общем, в приложениях для среды [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии 3.5 и более новой версии должны использоваться лямбда\-выражения.  
  
 В приведенном ниже примере демонстрируется эволюция создания делегата в языке C\# с версии 1.0 до версии 3.0.  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Инструкции, выражения и операторы](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)