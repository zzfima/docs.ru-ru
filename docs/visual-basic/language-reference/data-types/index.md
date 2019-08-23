---
title: Сводка типов данных (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
ms.openlocfilehash: 57f6caa00806f4874cb8070805e8b6784ec82e40
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956801"
---
# <a name="data-type-summary-visual-basic"></a>Сводка типов данных (Visual Basic)
В следующей таблице показаны типы данных Visual Basic, Поддерживаемые типы среды CLR, их номинальное выделение памяти и диапазоны значений.  
  
|Тип Visual Basic|Структура типа среды CLR|Номинальное выделение памяти|Диапазон значений|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Зависит от реализации платформы|`True` или `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 байт|от 0 до 255 (без знака)|  
|[Тип char](../../../visual-basic/language-reference/data-types/char-data-type.md) (одиночный символ)|<xref:System.Char>|2 байта|от 0 до 65535 (без знака)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 байт|0:00:00 (полночь) 1 января 0001 г. по 11:59:59 – 31 декабря 9999|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 байт|от 0 до +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9...E + 28) <sup>†</sup> без десятичной запятой; от 0 до +/-7.9228162514264337593543950335 с 28 разрядами справа от десятичного разделителя;<br /><br /> наименьшее ненулевое число — +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) (число двойной точности с плавающей запятой)|<xref:System.Double>|8 байт|-1.79769313486231570 e + 308 до-4.94065645841246544 E-324 <sup>†</sup> для отрицательных значений;<br /><br /> 4.94065645841246544 e-324 до 1.79769313486231570 E + 308 <sup>†</sup> для положительных значений|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 байта|от-2 147 483 648 до 2 147 483 647 (подписано)|  
|[Длинное целое](../../../visual-basic/language-reference/data-types/long-data-type.md) (длинное целое)|<xref:System.Int64>|8 байт|от-9223372036854775808 до 9 223 372 036 854 775 807 (от а до 18 <sup>†</sup>) (подписано)|  
|[Объект](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object>см|4 байта на 32-разрядной платформе<br /><br /> 8 байт на 64-разрядной платформе|Любой тип может храниться в переменной типа`Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 байт|от-128 до 127 (подписано)|  
|[Короткий формат](../../../visual-basic/language-reference/data-types/short-data-type.md) (короткое целое)|<xref:System.Int16>|2 байта|от-32 768 до 32 767 (подписано)|  
|[Один](../../../visual-basic/language-reference/data-types/single-data-type.md) (число с плавающей запятой одиночной точности)|<xref:System.Single>|4 байта|-4028235E e + 38 – 1.401298 E-45 <sup>†</sup> для отрицательных значений;<br /><br /> 1.401298 e-45 до 4028235E E + 38 <sup>†</sup> для положительных значений|  
|[Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) (переменная длина)|<xref:System.String>см|Зависит от реализации платформы|от 0 до приблизительно 2 000 000 000 символов Юникода|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 байта|от 0 до 4 294 967 295 (без знака)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 байт|от 0 до 18446744073709551615 (1.8... E + 19 <sup>†</sup>) (без знака)|  
|[Определяемые пользователем](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) дереве|(наследует от <xref:System.ValueType>)|Зависит от реализации платформы|Каждый элемент структуры имеет диапазон, определяемый типом данных и не зависящий от диапазонов других элементов.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 байта|от 0 до 65 535 (без знака)|  
  
 <sup>†</sup> В *экспоненциальном представлении*"E" означает степень числа 10. Итак, 3.56 E + 2 означает 3,56 x 10<sup></sup> или 356, а 3.56 e-2 — 3,56/10<sup>2</sup> или 0,0356.  
  
> [!NOTE]
> Для строк, содержащих текст, используйте <xref:Microsoft.VisualBasic.Strings.StrConv%2A> функцию для преобразования одного текстового формата в другой.  
  
 Помимо указания типа данных в операторе объявления, можно принудительно задать тип данных некоторых элементов программирования с помощью символа типа. См. раздел [символы типа](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Затраты памяти  
 При объявлении простейшего типа данных нельзя считать, что его потребление памяти совпадает с номинальным выделением хранилища. Это обусловлено следующими соображениями.  
  
- **Назначение хранилища.** Среда CLR может назначать хранилище на основе текущих характеристик платформы, в которой выполняются приложения. Если память почти заполнена, она может упаковать объявленные элементы как можно ближе друг к другу. В других случаях адреса памяти могут быть согласованы с естественными аппаратными границами для оптимизации производительности.  
  
- **Ширина платформы.** Назначение хранилища на 64-разрядной платформе отличается от назначения на 32-разрядной платформе.  
  
### <a name="composite-data-types"></a>Составные типы данных  
 Те же рекомендации применимы к каждому элементу составного типа данных, такому как структура или массив. Вы не можете полагаться на простое сложение номинальных выделений памяти для членов типа. Кроме того, существуют и другие рекомендации, например следующие:  
  
- **За.** Некоторые составные типы предъявляют дополнительные требования к памяти. Например, массив использует дополнительную память для самого массива, а также для каждого измерения. На 32-разрядной платформе этот объем накладных расходов в настоящее время составляет 12 байт плюс 8 байт для каждого измерения. На 64-разрядной платформе это требование удваивается.  
  
- **Структура хранилища.** Нельзя безопасно предположить, что порядок хранения в памяти совпадает с порядком объявления. Вы даже не можете делать предположения относительно выравнивания байтов, например 2-байтовой или 4-байтовой границы. При определении класса или структуры и необходимости управления структурой хранения его элементов можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут к классу или структуре.  
  
### <a name="object-overhead"></a>Издержки объекта  
 При `Object` ссылке на любой простой или составной тип данных в дополнение к данным, содержащимся в типе данных, используется 4 байта.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
