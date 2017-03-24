---
title: "out (Справочник по C#) | Microsoft Docs"
ms.date: "2017-03-01"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "out_CSharpKeyword"
  - "out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out [C#]"
  - "out - ключевое слово [C#]"
ms.assetid: 7e911a0c-3f98-4536-87be-d539b7536ca8
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# out (Справочник по C#)
Контекстно\-зависимое ключевое слово `out` можно использовать в двух контекстах \(каждый представляет собой ссылку на подробные сведения\) — как [модификатор параметра](../../../csharp/language-reference/keywords/out-parameter-modifier.md) или в [объявлениях параметра универсального типа](../../../csharp/language-reference/keywords/out-generic-modifier.md) в интерфейсах и делегатах.  В этом разделе содержатся сведения о модификаторе параметра, однако сведения об объявлениях параметра универсального типа см. в [в этом разделе](../../../csharp/language-reference/keywords/out-generic-modifier.md).  
  
 Ключевое `out` инициирует передачу аргументов по ссылке.  Оно схоже с ключевым словом [ref](../../../csharp/language-reference/keywords/ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.  Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.  Например:  
  
 [!code-cs[csrefKeywordsMethodParams#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/out_1.cs)]  
  
 Несмотря на то, что переменные, передаваемые как аргументы `out`, не нужно инициализировать перед передачей, для назначения значения требуется вызываемый метод.  
  
 Несмотря на то, что ключевые слова `ref` и `out` вызвать другое поведение среды выполнения, они не считаются частью подписи метода во время компиляции.  Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref`, а другой — аргумент `out`.  Следующий код, например, компилироваться не будет.  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/out_2.cs)]  
  
 Перегрузка возможна, если один метод принимает аргумент `ref` или `out`, а другой не использует ни одного из них, как показано далее.  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out_3.cs)]  
  
 Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.  
  
 Сведения об передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.  
  
-   Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Методы итератора, которые включают инструкцию [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  
  
## Пример  
 Объявление метода `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений.  В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.  Обратите внимание, что третьему аргумент присвоено значение null.  Это позволяет методам возвращать значения по желанию.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out_4.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)