---
title: Тип данных UInteger (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 4d93b1e40371b00f9d1ff69ec31ad0983beb493f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971734"
---
# <a name="uinteger-data-type"></a>UInteger - тип данных

Содержит 32 бита (4-байтовое) целых чисел без знака в диапазоне от 0 до 4 294 967 295.  
  
## <a name="remarks"></a>Примечания

 `UInteger` Тип данных предоставляет наибольшее значение без знака в наиболее эффективной ширине данных.  
  
 Значение по умолчанию для типа `UInteger` — 0.  
  
## <a name="literal-assignments"></a>Назначения литералов

Можно объявить и инициализировать `UInteger` переменной, назначив ей десятичный литерал, шестнадцатеричный восьмеричный литерал, или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> Используйте префикс `&h` или `&H` для обозначения шестнадцатеричного литерала, префикс `&b` или `&B` для обозначения двоичного литерала, а также префикс `&o` или `&O` для обозначения восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания, `_`, в качестве разделителя разрядов для повышения удобства чтения, как в примере ниже показан.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

Начиная с Visual Basic 15.5, можно также использовать символ подчеркивания (`_`) в качестве начального разделителя между префиксом и двоичное, шестнадцатеричное или восьмеричное цифры. Пример:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы могут содержать `UI` или `ui` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для обозначения `UInteger` тип данных, как показано в следующем примере.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Советы по программированию

 `UInteger` И `Integer` типы данных обеспечивает оптимальную производительность на 32-разрядный процессор, так как целочисленные типы меньшего размера (`UShort`, `Short`, `Byte`, и `SByte`), несмотря на то, что они используют меньшее число битов, занимает больше времени загрузки, хранения и извлечения.  
  
- **Отрицательные числа.** Так как `UInteger` — это тип без знака, он не может представлять отрицательное число. При использовании унарного минуса (`-`) оператор на выражение, результатом вычисления которого введите `UInteger`, Visual Basic преобразует выражение `Long` первого.  
  
- **CLS-совместимость.** `UInteger` Тип данных не является частью [спецификация CLS](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который его использует.
  
- **Вопросы взаимодействия.** При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, имейте в виду, что типы, такие как `uint` может иметь другой размер (16 бит) в других средах. Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.  
  
- **Расширяющие.** `UInteger` Тип данных можно расширить до `Long`, `ULong`, `Decimal`, `Single`, и `Double`. Это означает, что вы можете преобразовать `UInteger` к любому из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
- **Символы типа.** Добавление символы типа литерала `UI` в литерал приводит к принудительному `UInteger` тип данных. `UInteger` не имеет тип символа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.UInt32>
- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
