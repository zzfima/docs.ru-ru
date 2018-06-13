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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591798"
---
# <a name="data-type-summary-visual-basic"></a>Сводка типов данных (Visual Basic)
В следующей таблице показаны типы данных Visual Basic, их вспомогательные типами среды CLR, их выделение номинальный хранилища и их диапазоны значений.  
  
|Тип Visual Basic|Общая структура типа среды выполнения языка|Номинальной памяти|Диапазон значений|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Зависит от платформы реализации|`True` или `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 байт|от 0 до 255 (без знака)|  
|[Char-](../../../visual-basic/language-reference/data-types/char-data-type.md) (одиночный символ)|<xref:System.Char>|2 байта|от 0 до 65535 (без знака)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 байт|0:00:00 (полночь) 1 января 0001 года до 11:59:59 PM 31 декабря 9999 года|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 байт|от 0 до +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9... E + 28) <sup>†</sup> нет десятичной запятой; от 0 до +/-7,9228162514264337593543950335 с 28 разрядов справа от десятичной запятой;<br /><br /> наименьшее ненулевое значение — +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Двойные](../../../visual-basic/language-reference/data-types/double-data-type.md) (двойной точности с плавающей запятой)|<xref:System.Double>|8 байт|-1, 79769313486231570E + 308 до - 4.94065645841246544E-324 <sup>†</sup> для отрицательных значений;<br /><br /> 4.94065645841246544E-324 до 1, 79769313486231570E + 308 <sup>†</sup> для положительных значений|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 байта|от -2147483648 до 2 147 483 647 (со знаком)|  
|[Длинное](../../../visual-basic/language-reference/data-types/long-data-type.md) (длинное целое)|<xref:System.Int64>|8 байт|-9,223,372,036,854,775,808 до 9,223,372,036,854,775,807 (9.2... E + 18 <sup>†</sup>) (подписанный)|  
|[Объект](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (класс)|4 байта в 32-разрядной платформе<br /><br /> 8 байт на 64-разрядной платформе|Любой тип, которые могут храниться в переменной типа `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 байт|от -128 до 127 (со знаком)|  
|[Краткое](../../../visual-basic/language-reference/data-types/short-data-type.md) (короткое целое число)|<xref:System.Int16>|2 байта|-32 768 до 32 767 (со знаком)|  
|[Один](../../../visual-basic/language-reference/data-types/single-data-type.md) (одинарной точности с плавающей запятой)|<xref:System.Single>|4 байта|-3, 4028235E + 38 до - 1, 401298E-45 <sup>†</sup> для отрицательных значений;<br /><br /> 1, 401298E-45 до 3, 4028235E + 38 <sup>†</sup> для положительных значений|  
|[Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) (переменной длины)|<xref:System.String> (класс)|Зависит от платформы реализации|от 0 до приблизительно 2 миллиардов знаков Юникода|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 байта|от 0 до 4 294 967 295 (без знака)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 байт|от 0 до 18446744073709551615 (1.8... E + 19 <sup>†</sup>) (без знака)|  
|[Определяемые пользователем](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (структура)|(наследуется от <xref:System.ValueType>)|Зависит от платформы реализации|Каждый элемент структуры имеет диапазон, определяемый по его типу данных и не зависят от диапазонов других членов|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 байта|от 0 до 65 535 (без знака)|  
  
 <sup>†</sup> В *экспоненциальное представление чисел*, «E» ссылается на степень числа 10. Поэтому 3.56E + 2 означает 3.56 x 10<sup>2</sup> или 356 и 3.56E-2 означает 3.56 / 10<sup>2</sup> или 0.0356.  
  
> [!NOTE]
>  Для строк, содержащих текст, используйте <xref:Microsoft.VisualBasic.Strings.StrConv%2A> функцию для преобразования из одного текстового формата.  
  
 В дополнение к определению типов данных в операторе объявления, можно задать тип данных некоторых элементов программирования с помощью знака типа. В разделе [символов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Затраты памяти  
 При объявлении простейший тип данных не уверенностью предположить, что объем используемой памяти совпадает со значением номинальной памяти. Это происходит из-за следующее:  
  
-   **Выделение памяти.** Общеязыковая среда выполнения может назначить хранилище на основании текущих свойств платформы, на котором выполняется приложение. Если память почти заполнена, она может упаковать объявленные элементы близко друг к другу. В других случаях она может выравнять их адреса памяти для естественным аппаратным границам памяти для оптимизации производительности.  
  
-   **Ширина платформы.** Выделение памяти на 64-разрядной платформе отличается от выделения на 32-разрядной платформе.  
  
### <a name="composite-data-types"></a>Составные типы данных  
 Те же рекомендации применяются к каждому члену составной тип данных, таких как структура или массив. Не следует полагать, просто добавляя выделения Номинальное дисковое членов типа. Кроме того существуют другие вопросы, например следующие:  
  
-   **Дополнительные издержки.** Некоторые составные типы предъявляют дополнительные требования к памяти. Например массив использует дополнительную память для самого массива, а также для каждого измерения. В настоящее время на 32-разрядной платформе, эти накладные расходы — 12 байтов плюс 8 байт для каждого измерения. На 64-разрядной платформе эти требования удваиваются.  
  
-   **Расположение в памяти.** Вы не полагать, что порядок расположения элементов в памяти является таким же, как и порядок их объявления. Даже не может делать предположения о байтового выравнивания, например 2-байтовая или 4-байтовые границы. Если вы определяете класс или структуру и вам необходимо управлять его члены структуры хранилища, можно применить <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут в классе или структуре.  
  
### <a name="object-overhead"></a>Затраты на объект  
 `Object` Ссылок на данные в любой простой или составной тип использует 4 байта в дополнение к данным, содержащимся в тип данных.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Знаки типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
