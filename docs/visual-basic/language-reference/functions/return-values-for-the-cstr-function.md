---
title: Возвращаемые значения функции CStr
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349987"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Возвращаемые значения функции CStr (Visual Basic)
В следующей таблице описаны возвращаемые значения для `CStr` для различных типов данных `expression`.  
  
|Если `expression` тип —|Возвращаемые значения `CStr`|  
|-----------------------------|--------------------|  
|[Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Строка, содержащая "true" или "false".|  
|[Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Строка, содержащая значение `Date` (Дата и время) в кратком формате даты системы.|  
|[Числовые типы данных](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Строка, представляющая число.|  
  
## <a name="cstr-and-date"></a>Функция CStr и Дата  
 Тип `Date` всегда содержит сведения о дате и времени. В целях преобразования типов Visual Basic учитывает 1/1/0001 (1 января 1 года) как *нейтральное значение* для даты, а 00:00:00 (полночь) — как нейтральное значение времени. `CStr` не содержит нейтральные значения в результирующей строке. Например, при преобразовании `#January 1, 0001 9:30:00#` в строку результатом будет «9:30:00 AM»; сведения о дате подавляются. Однако сведения о дате по-прежнему содержатся в исходном значении `Date` и могут быть восстановлены с помощью таких функций, как <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
> Функция `CStr` выполняет свое преобразование на основе текущих настроек языка и региональных параметров для приложения. Чтобы получить строковое представление числа в определенном языке и региональных параметрах, используйте метод `ToString(IFormatProvider)` числа. Например, используйте <xref:System.Double.ToString%2A?displayProperty=nameWithType> при преобразовании значения типа `Double` в `String`.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Тип данных Date](../../../visual-basic/language-reference/data-types/date-data-type.md)
