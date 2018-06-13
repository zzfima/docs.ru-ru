---
title: Строковые функции (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: f6c7f28cee03c2d5ac258cf1e2c8956225334f7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604150"
---
# <a name="string-functions-visual-basic"></a>Строковые функции (Visual Basic)
Ниже перечислены функции, которые предоставляет Visual Basic для поиска и работы со строками.  
  
|Метод .NET framework|Описание|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Возвращает `Integer` значение, представляющее код заданного символа.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Возвращает символ, соответствующий заданному коду символа.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Возвращает отсчитываемый от нуля массив, содержащий подмножество `String` массива согласно указанным условиям фильтра.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Возвращает строку, отформатированную в соответствии с инструкциями, содержащимися в формате `String` выражение.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Возвращает выражение, отформатированное как денежная сумма с символа валюты, определенного в системной панели управления.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Возвращает строковое выражение, представляющее значение даты и времени.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Возвращает выражение, отформатированное как число.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Возвращает выражение в виде процента (умноженное на 100) с символом % в конце.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Возвращает целое число, указывающее начальную позицию первого вхождения одной строки в другую.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Возвращает позицию первого вхождения одной строки в другую, начиная с правой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Возвращает строку, созданную путем объединения нескольких подстрок, содержащихся в массиве.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Возвращает строку или символ, преобразованную в нижний регистр.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Возвращает строку, содержащую указанное количество символов с левой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Возвращает целое число, которое содержит число символов в строке.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Возвращает строку по левому краю, содержащую указанную строку, приведенную к заданной длине.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Возвращает строку, содержащую копию указанной строки без начальных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Возвращает строку, содержащую указанное число символов из строки.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Возвращает строку, в которой указанная подстрока заменена другой подстрокой заданное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Возвращает строку, содержащую указанное количество символов с правой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Возвращает строку с выравниванием по правому краю, содержащую указанную строку, приведенную к заданной длине.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Возвращает строку, содержащую копию указанной строки без конечных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Возвращает строку, состоящую из указанного числа пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Возвращает отсчитываемый от нуля одномерный массив, содержащий указанное число подстрок.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Возвращает значение -1, 0 или 1, в зависимости от результата сравнения строк.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Возвращает строку, преобразованную указанным образом.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Возвращает строку или объект, состоящие из указанного знака, повторенного указанное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Возвращает строку, в которой является обратным порядком символов в указанной строке.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Возвращает строку, содержащую копию указанной строки без начальных и конечных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Возвращает строку или символ, содержащий указанную строку, преобразованную в верхний регистр.|  
  
 Можно использовать [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) инструкции, чтобы задать ли сравнения строк без учета регистра текста с помощью сортировка, определяемого языком системы (`Text`) или внутренних двоичных представлений символов ( `Binary`). Метод сравнения текста по умолчанию — `Binary`.  
  
## <a name="example"></a>Пример  
 В этом примере используется `UCase` функции для возврата версии строки в верхнем регистре.  
  
 [!code-vb[VbVbalrStrings#31](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_1.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `LTrim` функцию для удаления начальных пробелов и `RTrim` функция, чтобы убрать замыкающие пробелы из строковой переменной. Она использует `Trim` функцию для удаления обоих типов пробелов.  
  
 [!code-vb[VbVbalrStrings#25](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` функция возвращает указанное количество символов из строки.  
  
 [!code-vb[VbVbalrStrings#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_3.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `Len` для возврата числа знаков в строке.  
  
 [!code-vb[VbVbalrStrings#33](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_4.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `InStr` функция возвращает позицию первого вхождения одной строки в другую.  
  
 [!code-vb[VbVbalrStrings#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_5.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере показаны различные способы использования `Format` функции для форматирования значений с помощью обоих `String` форматов и форматов, определенных пользователем. В качестве разделителя даты (`/`), разделитель компонентов времени (`:`) и индикаторов AM/PM (`t` и `tt`), Фактическое отображение системой зависит от параметров языкового стандарта, используя код. Если времени и даты будут выводиться в среде разработки, используются краткий формат даты и краткий формат код языкового стандарта.  
  
> [!NOTE]
>  Для языков, использующих 24-часовом формате, индикаторы AM/PM (`t` и `tt`) не отображаются.  
  
 [!code-vb[VbVbalrStrings#27](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_6.vb)]  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Члены библиотеки времени выполнения Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)  
 [Сводка по работе со строками](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
