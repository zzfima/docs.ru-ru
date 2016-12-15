---
title: "Оператор * (Справочник по C#) | Microsoft Docs"
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
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* - оператор [C#]"
  - "оператор умножения (*) [C#]"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор * (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор умножения \(`*`\), который вычисляет произведение двух операндов.  Кроме того, это оператор разыменования, позволяющий выполнять чтение и запись в указателе.  
  
## Заметки  
 Все числовые типы имеют предопределенные операторы умножения.  
  
 Оператор `*` используется также для объявления типов указателей и для разыменования указателей.  Этот оператор может использоваться только в небезопасных контекстах, обозначенных ключевым словом [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметра компилятора [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Оператор разыменования известен также как косвенный оператор.  
  
 Типы, определенные пользователем, могут вызвать перегрузку бинарного оператора `*` \(см [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## Пример  
 [!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)