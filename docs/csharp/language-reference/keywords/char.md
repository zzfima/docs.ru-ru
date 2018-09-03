---
title: Ключевое слово char (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 95ecfaaf1397f7a4598faba6528b38170062145a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43463225"
---
# <a name="char-c-reference"></a>char (Справочник по C#)

Ключевое слово `char` используется для объявления экземпляра структуры <xref:System.Char?displayProperty=nameWithType>, используемой .NET Framework для представления символа Юникода. Значение объекта `Char` представляет собой 16-разрядное числовое (порядковое) значение.

 Символы в кодировке Юникода используются для представления большинства письменных языков в мире.

|Тип|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------------------|
|`char`|От U+0000 до U+FFFF|Символ Юникода (16-разрядный)|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Литералы

Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода. Также можно выполнить приведение целочисленных кодов символов. В следующем примере четыре переменные `char` инициализируются с помощью одного символа `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Преобразования

Тип `char` может быть неявно преобразован в тип [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md). Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.

Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Char>  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
- [Строки](../../../csharp/programming-guide/strings/index.md)