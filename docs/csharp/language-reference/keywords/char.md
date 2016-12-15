---
title: "char (Справочник по C#) | Microsoft Docs"
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
  - "char"
  - "char_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "char - тип данных [C#]"
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# char (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `char` используется для объявления экземпляр структуры <xref:System.Char?displayProperty=fullName> которой .NET Framework используются для представления символ юникода.  Значение объекта `Char` 16 бит числовой \(порядковое значение\).  
  
 Символы юникода, используемые для представления письменных большинство языков по всему миру.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|---------|--------------|------------|----------------------------------|  
|`char`|от U\+0000 до U\+FFFF|16\-разрядный символ Юникода|<xref:System.Char?displayProperty=fullName>|  
  
## Литералы  
 Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape\-последовательности или представления Юникода.  Кроме того, можно привести коды целых символов.  В следующем примере показана инициализация четырех переменных `char` с одним и тем же символом `X`:  
  
 [!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## Преобразования  
 `char` можно неявно преобразовать в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  Однако неявные преобразования из других типов в тип `char` не существуют.  
  
 Тип <xref:System.Char?displayProperty=fullName> предоставляет несколько статических методов для работы со значениями `char`.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.Char>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)