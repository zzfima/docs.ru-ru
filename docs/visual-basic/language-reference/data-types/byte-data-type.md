---
title: Тип данных Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28189ab4ab1a9be9265d1cca020039b5302fb5d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="byte-data-type-visual-basic"></a>Тип данных Byte (Visual Basic)
Содержит 8-разрядное (1-байтовые) целых чисел без знака, в диапазоне от 0 до 255.

## <a name="remarks"></a>Примечания

Используйте `Byte` тип данных для хранения двоичных данных.  
  
Значение по умолчанию для типа `Byte` — 0.

## <a name="literal-assignments"></a>Литерал назначения

Можно объявить и инициализировать `Byte` переменной, назначив его десятичное литералом, Шестнадцатеричный литерал восьмеричного литерала, или (начиная с Visual Basic 2017 г) двоичный литерал. Если целочисленный литерал находится за пределами диапазона `Byte` (то есть, в том случае, если это меньше, чем <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше, чем <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целых чисел, равные 201, представленное в десятичном, шестнадцатеричном виде, и двоичные литералы производится неявное преобразование из [целое](integer-data-type.md) для `byte` значения.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Используйте префикс `&h` или `&H` для обозначения Шестнадцатеричный литерал префиксом `&b` или `&B` для обозначения двоичный литерал и префикс `&o` или `&O` для обозначения восьмеричного литерала. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017 г., можно также использовать знак подчеркивания `_`, как разделитель для повышения удобства чтения, как в следующем примере показано.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания (`_`) в качестве начальных разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Советы по программированию

-   **Отрицательные числа.** Поскольку `Byte` является тип без знака, он не может представлять отрицательное число. Если вы используете унарного минуса (`-`) оператор в выражении, вычисляется как тип `Byte`, Visual Basic преобразует выражение, `Short` первой.
  
-   **Преобразование форматов.** Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он автоматически выполняет преобразование между форматами данных. Двоичные данные, хранящиеся в `Byte` переменных и массивов сохраняется во время преобразования формата. Не следует использовать `String` переменной для двоичных данных, так как его содержимое может быть повреждено при преобразовании между форматами ANSI и Юникод.

-   **Расширяющие.** `Byte` Тип данных может быть расширен до `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, или `Double`. Это означает, что можно преобразовать `Byte` на любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.
  
-   **Символы типов.** `Byte` не имеет знак типа литерала или знак типа идентификатора.

-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Пример

 В следующем примере `b` — `Byte` переменной. Инструкции показывают диапазон значений переменной и приложение операторы сдвига разряда на него.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>См. также

 <xref:System.Byte?displayProperty=nameWithType>  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
