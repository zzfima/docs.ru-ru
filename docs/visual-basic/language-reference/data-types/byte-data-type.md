---
title: Тип данных Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 8c9787d52667dc026d3fe62ac7f4b3de7e838a93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519792"
---
# <a name="byte-data-type-visual-basic"></a>Тип данных Byte (Visual Basic)
Содержит 8-разрядное (1-байтовое) целых чисел без знака, в диапазоне от 0 до 255.

## <a name="remarks"></a>Примечания

Используйте `Byte` тип данных для хранения двоичных данных.  
  
Значение по умолчанию для типа `Byte` — 0.

## <a name="literal-assignments"></a>Назначения литералов

Можно объявить и инициализировать `Byte` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Byte` (то есть, в том случае, если это меньше, чем <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше, чем <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 201, представляются в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из [целое число](integer-data-type.md) для `byte` значения.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Советы по программированию

-   **Отрицательные числа.** Так как `Byte` — это тип без знака, он не может представлять отрицательное число. При использовании унарного минуса (`-`) оператор на выражение, результатом вычисления которого введите `Byte`, Visual Basic преобразует выражение `Short` первого.
  
-   **Преобразование форматов.** Visual Basic считывает или записывает файлы, или при его вызове библиотеки DLL, методы и свойства, он автоматически выполняет преобразование между форматами данных. Двоичные данные, хранящиеся в `Byte` переменных и массивов сохраняется во время преобразования формата. Не следует использовать `String` переменной для двоичных данных, так как его содержимое может быть повреждено во время преобразования между форматами ANSI и Юникод.

-   **Расширяющие.** `Byte` Тип данных можно расширить до `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`. Это означает, что вы можете преобразовать `Byte` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.
  
-   **Символы типа.** `Byte` не имеет знак типа литерала или знак типа идентификатора.

-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Пример

 В следующем примере `b` является `Byte` переменной. Инструкции показывают диапазона переменной и в нем приложение операторы сдвига разряда.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>См. также

- <xref:System.Byte?displayProperty=nameWithType>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
