---
title: "Оператор — (справочник по C#) | Microsoft Docs"
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
  - "-_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "- - оператор [C#]"
  - "оператор вычитания (-) [C#]"
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор — (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `-` может функционировать как унарный или как бинарный оператор.  
  
## Заметки  
 Унарные операторы `-` предопределены для всех числовых типов.  Результатом использования унарного оператора `-` для числового типа является арифметическое отрицательное значение операнда.  
  
 Бинарные операторы `-` предопределены для всех числовых типов и типов перечислений для вычитания второго операнда из первого.  
  
 Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.  
  
 Пользовательские типы могут вызвать перегрузку унарного оператора `-` и бинарного `-` операторов.  Дополнительные сведения см. в разделе [оператор](../../../csharp/language-reference/keywords/operator.md).  
  
## Пример  
 [!code-cs[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)