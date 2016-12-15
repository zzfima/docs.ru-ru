---
title: "Практическое руководство. Сравнение строк (Руководство по программированию в C#) | Microsoft Docs"
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
  - "сравнение строк [C#]"
  - "строки [C#], сравнение"
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Сравнение строк (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В результате сравнения строк оказывается, что одна строка больше или меньше другой, или что обе строки одинаковы.  Правила, используемые для определения результата, отличаются в зависимости от выполнения *порядкового сравнения* или *сравнения с учетом языка и региональных параметров*.  Для каждой отдельной задачи важно использовать соответствующий вид сравнения.  
  
 Используйте базовые порядковые сравнения при необходимости сравнить или отсортировать значения двух строк независимо от лингвистических соглашений.  В базовом порядковом сравнении \(`System.StringComparison.Ordinal`\) учитывается регистр, что означает необходимость соответствия символов двух строк: "and" — не то же, что "And" или "AND".  Часто используется вариация  `System.StringComparison.OrdinalIgnoreCase`, которая соответствует написаниям and, And и AND.  `StringComparison.OrdinalIgnoreCase` часто используется для сравнения имен файлов, имен путей, сетевых путей и любой другой строки, значение которой не меняется в зависимости от языка системы компьютера пользователя.  Дополнительные сведения см. в разделе <xref:System.StringComparison?displayProperty=fullName>.  
  
 Сравнения с учетом языка и региональных параметров обычно используются для сравнения и сортировки строк, введенных конечными пользователями, поскольку символы и правила сортировки этих строк могут отличаться в зависимости от языкового стандарта компьютера пользователя.  Даже строки, содержащие идентичные символы, могут быть отсортированы по\-разному, в зависимости от языка и региональных параметров текущего потока.  
  
> [!NOTE]
>  При сравнении строк следует использовать методы, которые явно указывают, какой вид сравнения следует выполнить.  Это делает код намного более поддерживаемым и удобочитаемым.  По возможности используйте перегрузки методов классов <xref:System.String?displayProperty=fullName> и <xref:System.Array?displayProperty=fullName>, которые принимают параметр перечисления <xref:System.StringComparison>, чтобы можно было задать тип выполнения сравнения.  По возможности рекомендуется избегать использования операторов `==` и `!=` при сравнении строк.  Также рекомендуется избегать использования методов экземпляра <xref:System.String.CompareTo%2A?displayProperty=fullName>, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.  
  
## Пример  
 В следующем примере показано, как правильно сравнивать строки, значения которых не изменятся на основе языкового стандарта компьютера пользователя.  Кроме того, здесь показано свойство C\# *изоляция строк*.  При объявлении программой двух или более идентичных переменных строк компилятор сохраняет их в одном расположении.  Вызвав метод <xref:System.Object.ReferenceEquals%2A>, можно увидеть, что две строки фактически ссылаются на один и тот же объект в памяти.  Используйте метод <xref:System.String.Copy%2A?displayProperty=fullName>, чтобы избежать изоляции, как показано в следующем примере.  
  
 [!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]  
  
## Пример  
 В следующем примере показано, как предпочтительно сравнивать строки с помощью методов <xref:System.String?displayProperty=fullName>, принимающих перечисление <xref:System.StringComparison>.  Обратите внимание, что методы экземпляра <xref:System.String.CompareTo%2A?displayProperty=fullName> здесь не используются, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.  
  
 [!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]  
  
## Пример  
 В следующем примере показано, как сортировать и производить поиск строк в массиве с учетом языка и региональных параметров с помощью статических методов <xref:System.Array>, принимающих параметр <xref:System.StringComparer?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]  
  
 Классы коллекций, например <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> и <xref:System.Collections.Generic.List%601?displayProperty=fullName>, имеют конструкторы, принимающие параметр <xref:System.StringComparer?displayProperty=fullName>, когда типом элементов или ключей является `string`.  В целом, по возможности следует использовать эти конструкторы и задавать либо `Ordinal`, либо `OrdinalIgnoreCase`.  
  
## См. также  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Сравнение строк](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)   
 [Глобализация и локализация приложений](/visual-studio/ide/globalizing-and-localizing-applications)