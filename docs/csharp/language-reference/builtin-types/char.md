---
title: Тип char. Справочник по C#
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 3b2eec4f0e17aa329fe3865fb3ef453ee030c6a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450844"
---
# <a name="char-c-reference"></a>char (Справочник по C#)

Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.

|Тип|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------------------|
|`char`|От U+0000 до U+FFFF|16 разрядов|<xref:System.Char?displayProperty=nameWithType>|

Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.

## <a name="literals"></a>Литералы

Значение `char` можно указать следующим образом:

- символьный литерал;
- escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;
- шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.

> [!NOTE]
> В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры. То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.
>
> В случае шестнадцатеричной escape-последовательности начальные нули можно опустить. То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.

## <a name="conversions"></a>Преобразования

Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`. Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`. Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.

Неявные преобразования из других типов в тип `char` не предусмотрены. Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Таблица встроенных типов](../keywords/built-in-types-table.md)
- [Строки](../../programming-guide/strings/index.md)
