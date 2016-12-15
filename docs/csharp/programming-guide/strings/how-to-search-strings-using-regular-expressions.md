---
title: "Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#) | Microsoft Docs"
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
  - "поиск строк [C#]"
  - "строки [C#], поиск при помощи регулярных выражений"
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> можно использовать для поиска строк.  Поиск может отличаться по сложности и быть как простым, так и интенсивно использовать регулярные выражения.  Ниже приведены два примера поиска строк с помощью класса <xref:System.Text.RegularExpressions.Regex>.  Дополнительные сведения см. в разделе [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md).  
  
## Пример  
 Следующий пример кода является консольным приложением, которое выполняет простой поиск строк в массиве без учета регистра.  Статический метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> выполняет поиск заданной строки и строки, содержащей шаблон поиска.  В этом случае третий аргумент указывает, что регистр знаков следует игнорировать.  Дополнительные сведения см. в разделе <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## Пример  
 Следующий пример кода является консольным приложением, которое использует регулярные выражения для проверки формата каждой строки массива.  Для выполнения проверки требуется преобразование каждой строки в формат телефонного номера, в котором три группы цифр разделены дефисами, первые две группы содержат три цифры, а третья группа — четыре цифры.  Для этого используется регулярное выражение `^\\d{3}-\\d{3}-\\d{4}$`.  Дополнительные сведения см. в разделе [Элементы языка регулярных выражений — краткий справочник](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## См. также  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [Элементы языка регулярных выражений — краткий справочник](../Topic/Regular%20Expression%20Language%20-%20Quick%20Reference.md)