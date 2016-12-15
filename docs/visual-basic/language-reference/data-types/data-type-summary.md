---
title: "Сводка типов данных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "boolean - тип данных, поддерживаемые типы в Visual Basic"
  - "Byte - тип данных, типы данных Visual Basic"
  - "Char - тип данных, типы данных Visual Basic"
  - "типы данных [Visual Basic], требования к памяти"
  - "типы данных [Visual Basic], порядок хранения"
  - "типы данных [Visual Basic], область хранения"
  - "типы данных [Visual Basic], сводка"
  - "типы данных [Visual Basic], Visual Basic"
  - "Date - тип данных, Visual Basic"
  - "даты [Visual Basic], типы данных"
  - "Double - тип данных, типы данных Visual Basic"
  - "числа двойной точности"
  - "Integer - тип данных, типы данных Visual Basic"
  - "встроенные типы данных"
  - "Long - тип данных, поддерживаемые типы в Visual Basic"
  - "расход памяти"
  - "расход памяти, типы данных"
  - "требования к памяти, типы данных"
  - "нотация, экспоненциальный"
  - "Object - тип данных, поддерживаемые типы в Visual Basic"
  - "экспоненциальное представление чисел"
  - "Single - тип данных, поддерживаемые типы в Visual Basic"
  - "числа одинарной точности"
  - "порядок хранения, контролирование в Visual Basic"
  - "порядок хранения, типы данных"
  - "хранение, расположение"
  - "хранение, порядок хранения"
  - "хранение, пространство"
  - "String - тип данных, типы данных Visual Basic"
  - "строки [Visual Basic], типы данных"
  - "StructLayoutAttribute - класс, хранилище типа данных Visual Basic"
  - "пользовательские типы данных, Visual Basic"
  - "Variant - типы данных, поддерживаемые типы в Visual Basic"
  - "Visual Basic, типы данных"
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Сводка типов данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В следующей таблице описаны типы данных Visual Basic, поддерживающие их типы среды CLR, номинально занимаемая память и диапазоны значений.  
  
|Тип Visual Basic|Структура типа в среде CLR|Номинальная занимаемая память|Диапазон значений|  
|----------------------|--------------------------------|-----------------------------------|-----------------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Зависит от платформы реализации|`True` или `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 байт|От 0 до 255 \(беззнаковый\).|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) \(один знак\)|<xref:System.Char>|2 байта|От 0 до 65535 \(беззнаковый\).|  
|[Дата](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 байтов|От 0:00:00 \(полночь\) 1 января 0001 года до 11:59:59 вечера 31 декабря 9999 года.|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 байта|От 0 до \+\/–79 228 162 514 264 337 593 543 950 335 \(\+\/–7,9... E \+ 28\) <sup>†</sup> без десятичной запятой; от 0 до \+\/–7,9228162514264337593543950335 с 28 разрядами справа от десятичной запятой;<br /><br /> наименьшее ненулевое число — это \+\/–0,0000000000000000000000000001 \(\+\/–1E–28\) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) \(число двойной точности с плавающей запятой\)|<xref:System.Double>|8 байтов|От –1,79769313486231570E\+308 до –4.94065645841246544E–324 <sup>†</sup> для отрицательных значений;<br /><br /> от 4,94065645841246544E–324 до 1,79769313486231570E\+308 <sup>†</sup> для положительных значений|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 байта|От –2 147 483 648 до 2 147 483 647 \(знаковый\)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) \(длинное целое число\)|<xref:System.Int64>|8 байтов|От –9 223 372 036 854 775 808 до 9 223 372 036 854 775 807 \(9,2... E\+18 <sup>†</sup>\) \(знаковый\)|  
|[Объект.](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> \(класс\)|4 байта на 32\-разрядной платформе<br /><br /> 8 байт на 64\-разрядной платформе|В переменной типа `Object` может храниться значение любого типа.|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 байт|От –128 до 127 \(знаковый\)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md) \(короткое целое число\)|<xref:System.Int16>|2 байта|От –32 768 до 32 767 \(знаковый\)|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) \(число одиночной точности с плавающей запятой\)|<xref:System.Single>|4 байта|От –3,4028235E\+38 до –1,401298E–45 <sup>†</sup> для отрицательных значений;<br /><br /> от 1,401298E–45 до 3,4028235E\+38 <sup>†</sup> для положительных значений|  
|[String](../../../visual-basic/language-reference/data-types/string-data-type.md) \(строка переменной длины\)|<xref:System.String> \(класс\)|Зависит от платформы реализации|От 0 до приблизительно 2 миллиардов знаков в кодировке Юникод.|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 байта|От 0 до 4 294 967 295 \(беззнаковый\).|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 байтов|От 0 до 18 446 744 073 709 551 615 \(1,8... E\+19 <sup>†</sup>\) \(знаковый\)|  
|[Пользовательский тип](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) \(структура\)|\(наследует от <xref:System.ValueType>\)|Зависит от платформы реализации|Каждый член структуры имеет диапазон, определяемый его типом данных и не зависящий от диапазонов других членов.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 байта|От 0 до 65 535 \(беззнаковый\)|  
  
 <sup>†</sup> В *экспоненциальном представлении чисел* "E" ссылается на степень 10.  Таким образом, запись "3,56E \+ 2" равна 3.56 x 10<sup>2</sup>, или 356, а запись "3,56E \- 2" равна 3.56 \/ 10<sup>2</sup>, или 0,0356.  
  
> [!NOTE]
>  Для преобразования строк, содержащих текст, из одного текстового формата в другой, следует использовать функцию <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.  
  
 Помимо указания типа данных в инструкцию объявления, можно по тип данных некоторых элементов программирования с помощью символа типа.  Дополнительные сведения см. в разделе [Символы типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Затраты памяти  
 Нельзя полагать, что при объявлении простого типа данных выделяемая для него память будет соответствовать номинальной памяти, занимаемой этим типом данных.  Причиной тому следующие соображения:  
  
-   **Выделение памяти.** В среде CLR количество выделяемой памяти зависит от текущих свойств платформы, на которой выполняется приложение.  Если память почти заполнена, она может упаковать объявленные элементы вместе максимально плотно.  В других случаях она может выравнять их адреса в памяти до по естественной аппаратной границе для повышения производительности.  
  
-   **Разрядность платформы.** Выделение памяти на 64\-разрядной платформе отличается от выделения памяти на 32\-разрядной платформе.  
  
### Составные типы данных  
 Аналогичные рассуждения справедливы для любых членов составных типов данных, таких как структура или массив.  Неверно основывать расчет требуемой памяти на простом сложении номинальных объемов памяти, занимаемых членами типа.  Кроме того, существуют другие вопросы, например:  
  
-   **Дополнительные издержки.** Некоторые составные типы расходуют дополнительный объем памяти.  Например, массив занимает дополнительную память для самого массива и для каждого измерения.  В настоящее время на 32\-разрядной платформе эти дополнительные издержки составляет 12 байтов плюс по 8 байтов для каждого измерения.  На 64\-разрядной платформе эти требования удваиваются.  
  
-   **Расположение в памяти.** Нельзя однозначно полагать, что порядок расположения элементов в памяти соответствует порядку их объявления.  Нельзя даже делать какие\-либо предположения о порядке выравнивании байтов, таких как 2\-байтовая или 4\-байтовая границы.  Если при определении класса или структуры требуется контролировать расположение членов в памяти, то к классу или структуре можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>.  
  
### Служебные данные типа Object  
 Переменная типа `Object`, ссылающаяся на любой простой или составной тип данных, использует 4 байта помимо данных, содержащихся в этом типе.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Символы типов](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)