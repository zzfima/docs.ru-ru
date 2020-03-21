---
title: Тип данных Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401355"
---
# <a name="byte-data-type-visual-basic"></a>Тип данных Байта (Visual Basic)

Держит неподписанные 8-битные (1-байт) целые столбики, которые варьируются в значении от 0 до 255.

## <a name="remarks"></a>Remarks

Используйте `Byte` тип данных для хранения двоичных данных.  
  
Значение по умолчанию для типа `Byte` — 0.

## <a name="literal-assignments"></a>Литературные задания

Вы можете объявить `Byte` и инициализировать переменную, назначив ей десятичную буквальную, гексадецичную буквальную, октальную буквальную или (начиная с Visual Basic 2017) двоичный буквальный. Если интегральный буквальный находится за `Byte` пределами диапазона (т.е. если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или <xref:System.Byte.MaxValue?displayProperty=nameWithType>больше), происходит ошибка компиляции.

В следующем примере целые штаты, равные 201, которые представлены как десятичные, гексадецимальные и `byte` двоичные буквальные, неявно преобразуются из [Integer](integer-data-type.md) в значения.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Вы используете `&h` приставку или `&H` для обозначения гексадецимального буквального, приставки `&b` или `&B` для `&o` `&O` обозначения двоичного буквального, и приставки или для обозначения октал буквального. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, вы также `_`можете использовать символ подчеркивания, как цифровой сепаратор для повышения читаемости, как показано в следующем примере.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Начиная с Visual Basic 15.5, вы также`_`можете использовать символ подчеркивателя ( ) в качестве ведущего сепаратора между приставкой и гексадецичными, бинарными или октальными цифрами. Пример:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** Поскольку `Byte` он является неподписанным типом, он не может представлять отрицательное число. Если вы используете необезыщаемый минус`-` `Byte`() оператора на выражение, которое оценивает вводить, Visual Basic преобразует выражение в `Short` первое.
  
- **Преобразование формата.** Когда Visual Basic читает или пишет файлы, или когда он вызывает DLLs, методы и свойства, он может автоматически конвертировать между форматами данных. Двоичные `Byte` данные, хранящиеся в переменных и массивах, сохраняются во время таких преобразований формата. Не следует использовать `String` переменную для двоичных данных, так как ее содержимое может быть повреждено при преобразовании между форматами ANSI и Unicode.

- **Расширение.** Тип `Byte` данных расширяется `UShort` `Integer`до `UInteger` `Short`, `ULong` `Decimal`, `Single`, `Double` `Long`, , , или . Это означает, `Byte` что вы можете преобразовать <xref:System.OverflowException?displayProperty=nameWithType> в любой из этих типов, не сталкиваясь с ошибкой.
  
- **Тип символов.** `Byte`не имеет буквального символа типа или символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Пример

 В следующем примере `b` `Byte` является переменной. Заявления демонстрируют диапазон переменной и применение к ней операторов бит-сдвига.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>См. также раздел

- <xref:System.Byte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
