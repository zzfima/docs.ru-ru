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
ms.openlocfilehash: 255e69d3715a22e7933b4036e968e610657748cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353768"
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
- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [Целочисленные типы](../builtin-types/integral-numeric-types.md)
- [Таблица встроенных типов](./built-in-types-table.md)
- [Таблица неявных числовых преобразований](./implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](./explicit-numeric-conversions-table.md)
- [Строки](../../programming-guide/strings/index.md)
