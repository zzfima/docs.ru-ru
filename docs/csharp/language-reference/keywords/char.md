---
title: Справочник по C#. Ключевое слово char
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: b58730d945582ded7b76fcd5c4c65bc1dd9324da
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661458"
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

Тип `char` может быть неявно преобразован в тип [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) или [decimal](../builtin-types/floating-point-numeric-types.md). Тем не менее неявные преобразования из других типов в тип `char` не предусмотрены.

Тип <xref:System.Char?displayProperty=nameWithType> предоставляет несколько статических методов для работы со значениями `char`.

## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- <xref:System.Char>
- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
- [Целочисленные типы](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)
- [Строки](../../../csharp/programming-guide/strings/index.md)
