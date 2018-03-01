---
title: "char (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a>char (Справочник по C#)
Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода. Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.  
  
 Символы в кодировке Юникода используются для представления большинства письменных языков в мире.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`char`|От U+0000 до U+FFFF|Символ Юникода (16-разрядный)|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Литералы  
 Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода. Также можно выполнить приведение целочисленных кодов символов. В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a>Преобразования  
 Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md). Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.  
  
 Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Char>  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [Строки](../../../csharp/programming-guide/strings/index.md)
