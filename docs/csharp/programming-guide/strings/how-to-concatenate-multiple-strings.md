---
title: "Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "сцепление строк [C#]"
  - "объединение строк [C#]"
  - "строки [C#], объединение"
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)
*Объединение* — это процесс добавления одной строки к концу другой.  При объединении строковых литералов или строковых констант с помощью оператора `+` компилятор создает одну строку.  Объединение среды выполнения не происходит.  Однако строковые переменные могут быть объединены только во время выполнения.  В таком случае следует уяснить влияние различных подходов на производительность.  
  
## Пример  
 В следующем примере показано разделение длинного строкового литерала на маленькие строки для повышения удобочитаемости в исходном коде.  Во время компиляции эти части будут объединены в одну строку.  Производительность не снижается, независимо от количества используемых строк.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## Пример  
 Для объединения строковых переменных можно использовать операторы `+` или `+=` или методы <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.  Оператор `+` прост в использовании и позволяет сформировать наглядный код.  Даже при одновременном использовании нескольких операторов "\+" содержимое строки копируется только один раз.  Однако если повторить такую операцию несколько раз \(например, в цикле\), могут возникнуть проблемы с производительностью.  Например, рассмотрим следующий код:  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  В операциях объединения строк компилятор С\# обрабатывает нулевую строку так же, как пустую строку, но не преобразовывает значение исходной нулевой строки.  
  
 Если не выполняется объединения большого количества строк \(например, в цикле\), то снижение производительности этого кода, вероятно, будет незначительным.  Это также относится к методам <xref:System.String.Concat%2A?displayProperty=fullName> и <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 Однако, если самым важным является производительность, то для объединения строк всегда следует использовать класс <xref:System.Text.StringBuilder>.  В следующем коде используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder> для объединения строк без "эффекта цепочки" оператора `+`.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## См. также  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)