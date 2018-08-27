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
ms.openlocfilehash: 8afeba3f88c4bfe6e1c9777f950c3b458665e340
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925897"
---
# <a name="data-type-summary-visual-basic"></a>Сводка типов данных (Visual Basic)
Ниже приведены типы данных Visual Basic, их вспомогательные типами среды CLR, номинально занимаемая память и их диапазоны значений.  
  
|Тип Visual Basic|Общая структура типа среды выполнения языка|Номинальной памяти|Диапазон значений|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Зависит от реализации платформы|`True` или `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 байт|от 0 до 255 (неподписанный)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (один знак)|<xref:System.Char>|2 байта|от 0 до 65535 (без знака)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 байт|0:00:00 (полночь) 1 января 0001 года до 23:59:59: 00 31 декабря 9999 года|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 байт|от 0 до +/-79,228,162,514,264,337,593,543,950,335 (+/-7,9 … E + 28) <sup>†</sup> нет десятичной запятой; от 0 до +/-7,9228162514264337593543950335 с 28 разрядами справа от десятичного разделителя;<br /><br /> наименьшее ненулевое значение равно +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) (двойной точности с плавающей запятой)|<xref:System.Double>|8 байт|-1, 79769313486231570E + 308 до - 4.94065645841246544E-324 <sup>†</sup> для отрицательных значений;<br /><br /> 4.94065645841246544E-324 до 1, 79769313486231570E + 308 <sup>†</sup> для положительных значений|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 байта|от -2147483648 до 2 147 483 647 (со знаком)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) (длинное целое)|<xref:System.Int64>|8 байт|-9223372036854775808 до 9223372036854775807 (9.2 … E + 18 <sup>†</sup>) (со знаком)|  
|[Объект](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (класс)|4 байта в 32-разрядной платформе<br /><br /> 8 байт на 64-разрядной платформе|Любой тип, которые могут храниться в переменной типа `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 байт|-128 до 127 (со знаком)|  
|[Короткий](../../../visual-basic/language-reference/data-types/short-data-type.md) (короткое целое число)|<xref:System.Int16>|2 байта|-32 768 до 32 767 (со знаком)|  
|[Единый](../../../visual-basic/language-reference/data-types/single-data-type.md) (одиночной точности с плавающей запятой)|<xref:System.Single>|4 байта|-3, 4028235E + 38 до - 1, 401298E-45 <sup>†</sup> для отрицательных значений;<br /><br /> 1, 401298E-45 до 3, 4028235E + 38 <sup>†</sup> для положительных значений|  
|[Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) (переменной длины)|<xref:System.String> (класс)|Зависит от реализации платформы|0 до приблизительно 2 миллиардов знаков Юникода|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 байта|от 0 до 4 294 967 295 (неподписанный)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 байт|от 0 до 18446744073709551615 (1,8 … E + 19 <sup>†</sup>) (без знака)|  
|[Определяемые пользователем](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (структуры)|(наследуется от <xref:System.ValueType>)|Зависит от реализации платформы|Каждый элемент структуры имеет диапазон, определяемый по его типу данных и не зависят от диапазонов других элементов|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 байта|от 0 до 65 535 (неподписанный)|  
  
 <sup>†</sup> В *экспоненциальное представление чисел*, «E» ссылается на степень числа 10. Поэтому 3.56E + 2 означает 3.56 x 10<sup>2</sup> или 356 и 3.56E-2 означает, что 3.56 / 10<sup>2</sup> или 0.0356.  
  
> [!NOTE]
>  Для строк, содержащих текст, используйте <xref:Microsoft.VisualBasic.Strings.StrConv%2A> функция для преобразования из одного текстового формата в другой.  
  
 В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с помощью символа типа. См. в разделе [символов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Затраты памяти  
 При объявлении простой тип данных, не уверенностью предположить, что объем используемой памяти совпадает со значением номинальной памяти. Это происходит из-за следующее:  
  
-   **Назначение хранилища.** Среда CLR может назначать хранилище, с учетом характеристик текущей платформы, на котором выполняется приложение. Если памяти почти заполнен, она может упаковать объявленные элементы близко друг к другу. В других случаях он может выровнять их адреса памяти для естественным аппаратным границам памяти для оптимизации производительности.  
  
-   **Ширина платформы.** Выделение памяти на 64-разрядной платформе отличается от назначения на 32-разрядной платформе.  
  
### <a name="composite-data-types"></a>Составные типы данных  
 Эти же рекомендации будут применимы к каждому члену типа составных данных, например структуру или массив. Нельзя полагаться на просто добавляя Номинальное дисковое распределения членов типа. Кроме того существуют и другие вопросы, например следующие:  
  
-   **Дополнительные издержки.** Некоторые составные типы имеют дополнительные требования к памяти. Например массив использует дополнительную память для самого массива, а также для каждого измерения. В настоящее время на 32-разрядной платформе, эти накладные расходы — 12 байт, а также 8 байт для каждого измерения. На 64-разрядной платформе удваивается это требование.  
  
-   **Расположение в памяти.** Нельзя рассчитывать на безопасно порядок элементов в памяти: так же, как порядок их объявления. Даже не может делать предположения о байтового выравнивания, например двухбайтовых и четырехбайтовых границ. Если при определении класса или структуры и вам необходимо управлять его члены структуры хранилища, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут класса или структуры.  
  
### <a name="object-overhead"></a>Затраты на объект  
 `Object` Ссылок на данные в любой простой или составной тип занимающего 4 байта в дополнение к данным, содержащимся в тип данных.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
