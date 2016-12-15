---
title: "Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "преобразования [C#], шестнадцатеричные строки"
  - "шестнадцатеричные строки [C#]"
  - "шестнадцатеричные строки [C#], преобразование в числовой тип"
  - "строки [C#], преобразование шестнадцатеричных строк"
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующих примерах показано выполнение следующих задач:  
  
-   Получите шестнадцатеричное значение каждого символа в [string](../../../csharp/language-reference/keywords/string.md).  
  
-   Получите [char](../../../csharp/language-reference/keywords/char.md), соответствующее каждому значению в шестнадцатеричной строке.  
  
-   Преобразование шестнадцатеричного значения `string` в [int](../../../csharp/language-reference/keywords/int.md).  
  
-   Преобразование шестнадцатеричного значения `string` в [float](../../../csharp/language-reference/keywords/float.md).  
  
-   Преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричное значение `string`.  
  
## Пример  
 Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`.  Сначала выполняется разбор `string` до массива символов.  Затем для каждого символа вызывается метод <xref:System.Convert.ToInt32%28System.Char%29> для получения его числового значения.  В конце, формат номера меняется на шестнадцатеричный в `string`.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## Пример  
 Этот пример выполняет разбор `string` шестнадцатеричных значений и выводит символ, соответствующий каждому шестнадцатеричному значению.  Сначала вызывается метод [Split\(Char\[\]\)](assetId:///M:System.String.Split(System.Char[])?qualifyHint=False&autoUpgrade=False) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве.  Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> для преобразования шестнадцатеричного значения в десятичное, представленное в формате [int](../../../csharp/language-reference/keywords/int.md).  В примере показано два разных способа получения символа, соответствующего этому коду символа.  В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, возвращающий символ, который соответствует целочисленному аргументу в виде `string`.  По второму способу выполняется явное приведение `int` к [char](../../../csharp/language-reference/keywords/char.md).  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## Пример  
 В следующем примере показан еще один способ преобразования шестнадцатеричного `string` в целое число путем вызова метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## Пример  
 В следующем примере показано преобразование шестнадцатеричного `string` в [float](../../../csharp/language-reference/keywords/float.md) с помощью класса <xref:System.BitConverter?displayProperty=fullName> и метода <xref:System.Int32.Parse%2A?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## Пример  
 В следующем примере показано преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## См. также  
 [Строки стандартных числовых форматов](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)