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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344082"
---
# <a name="byte-data-type-visual-basic"></a>Тип данных Byte (Visual Basic)

Содержит 8-битные (1-байтные) целые числа без знака в диапазоне от 0 до 255.

## <a name="remarks"></a>Примечания

Используйте `Byte` тип данных для хранения двоичных данных.  
  
Значение по умолчанию для типа `Byte` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать переменную `Byte`, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 201, представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целого числа](integer-data-type.md) в `byte` значения.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Префикс `&h` или `&H` можно использовать для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а префикс `&o` или `&O` — для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 можно также использовать символ подчеркивания `_`в качестве разделителя цифр для повышения удобочитаемости, как показано в следующем примере.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Начиная с Visual Basic 15,5 можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример.

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** Поскольку `Byte` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса (`-`) в выражении, результатом которого является тип `Byte`, Visual Basic сначала преобразует выражение в `Short`.
  
- **Преобразования формата.** Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он может автоматически выполнять преобразование между форматами данных. Двоичные данные, хранящиеся в переменных `Byte` и массивах, сохраняются во время таких преобразований формата. Не следует использовать переменную `String` для двоичных данных, так как ее содержимое может быть повреждено во время преобразования между форматами ANSI и Юникод.

- **Расширяющие.** Тип данных `Byte` расширяется на `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`или `Double`. Это означает, что можно преобразовать `Byte` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.
  
- **Символы типа.** `Byte` не имеет символа типа литерала или символа типа идентификатора.

- **Тип платформы.** В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Пример

 В следующем примере `b` является переменной `Byte`. Инструкции демонстрируют диапазон переменных и применение к нему операторов побитового сдвига.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>См. также

- <xref:System.Byte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
