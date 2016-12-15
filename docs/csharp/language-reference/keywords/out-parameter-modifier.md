---
title: "Модификатор параметров out (справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "параметры out [C#]"
  - "параметры [C#], out"
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Модификатор параметров out (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `out` используется для передачи аргументов по ссылке.  Оно похоже на ключевое слово [ref](../../../csharp/language-reference/keywords/ref.md), за исключением того, что `ref` требует инициализации переменной перед ее передачей.  Для работы с параметром `out` определение метода и вызывающий метод должны явно использовать ключевое слово `out`.  Примеры.  
  
 [!code-cs[csrefKeywordsMethodParams#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_1.cs)]  
  
 Несмотря на то что переменные, передаваемые в качестве аргументов `out`, могут не инициализироваться перед передачей, вызываемый метод должен присвоить значение перед возвратом метода.  
  
 Ключевые слова `ref` и `out` приводят к разным результатам во время выполнения, однако во время компиляции они не считаются частью сигнатуры метода.  Поэтому, если единственное различие между методами заключается в том, что один метод принимает аргумент `ref`, а другой — `out`, они не могут быть перегружены.  Следующий пример кода не будет компилироваться.  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_2.cs)]  
  
 Однако перегрузка возможна, если один метод принимает аргумент `ref` или `out`, а другой не принимает ни одного, как показано в следующем примере:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_3.cs)]  
  
 Свойства не являются переменными и поэтому не могут быть переданы в качестве параметров `out`.  
  
 Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Нельзя использовать ключевые слова `ref` и `out` для следующих типов методов:  
  
-   Методы Async, которые можно указать с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Методы итератора, которые включают формулировку [получение выходных данных](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  
  
## Пример  
 Объявление метода `out` используется тогда, когда необходимо, чтобы метод возвращал несколько значений.  В следующем примере используется ключевое слово `out` для возврата трех переменных с помощью одного вызова метода.  Обратите внимание, что третьему аргументу начинается значение 0.  Это позволяет методам возвращать значения на выбор.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)