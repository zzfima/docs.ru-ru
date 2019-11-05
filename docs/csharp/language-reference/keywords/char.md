---
title: Ключевое слово char — справочник по C#
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771801"
---
# <a name="char-c-reference"></a>char (Справочник по C#)

Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде:

|Тип|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------------------|
|`char`|От U+0000 до U+FFFF|16 разрядов|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Литералы

Константы типа `char` могут быть записаны в виде символьных литералов, шестнадцатеричной escape-последовательности или представления Юникода. Можно также привести целочисленный код символа к соответствующему значению `char`. В следующем примере четыре элемента массива `char` инициализируются с помощью одного символа `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Преобразования

Тип `char` неявно преобразуется в следующие [целочисленные](../builtin-types/integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`. Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](../builtin-types/floating-point-numeric-types.md): `float`, `double` и `decimal`. Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.

Неявные преобразования из других типов в тип `char` не предусмотрены. Но любой [целочисленный тип](../builtin-types/integral-numeric-types.md) или числовой тип [с плавающей запятой](../builtin-types/floating-point-numeric-types.md) явно преобразуется в `char`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Ключевые слова C#](./index.md)
- [Таблица встроенных типов](./built-in-types-table.md)
- [Строки](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
