---
title: "Практическое руководство. Преобразование из устаревших кодировок в Юникод (Руководство по программированию в C#) | Microsoft Docs"
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
  - "преобразования [C#], преобразование из устаревших кодировок в Юникод"
  - "строки [C#], преобразование между кодировками"
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Преобразование из устаревших кодировок в Юникод (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# все строки в памяти кодируются как Юникод \(UTF\-16\).  При переносе данных из места хранения в объект `string`, данные автоматически преобразуются в UTF\-16.  Если данные содержат только ASCII\-значения от 0 до 127, для преобразования не требуется никаких дополнительных действий.  Но если исходный текст содержит дополнительные байтовые значения ASCII \(от 128 до 255\), дополнительные символы по умолчанию интерпретируются в соответствии с текущей кодовой страницей.  Чтобы указать, что исходный текст нужно интерпретировать в соответствии с другой кодовой страницей, используйте класс <xref:System.Text.Encoding?displayProperty=fullName>, как показано в следующем примере.  
  
## Пример  
 В следующем примере показано, как преобразовать текстовый файл, который был закодирован в 8\-битном коде ASCII, интерпретируя исходный текст в соответствии с кодовой страницей Windows 737.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## См. также  
 [Строки](../../../csharp/programming-guide/strings/index.md)