---
title: Строковые функции (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 645d19219481d22ade90f44aaecb62471eb915d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802005"
---
# <a name="string-functions-visual-basic"></a>Строковые функции (Visual Basic)
Ниже перечислены функции, предоставляемые Visual Basic для поиска и работы со строками.  
  
|Метод .NET framework|Описание|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Возвращает `Integer` значение, представляющее код знака, соответствующий знаку.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Возвращает символ, связанный с указанным кодом знака.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Возвращает отсчитываемый от нуля массив, содержащий подмножество `String` выделяемое согласно указанным условиям фильтрации.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Возвращает строку, отформатированную в соответствии с инструкциями, содержащимися в формате `String` выражение.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Возвращает выражение, отформатированное в виде значения валюты с использованием символа валюты, определенного в системной панели управления.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Возвращает строковое выражение, представляющее значение даты и времени.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Возвращает выражение, отформатированное как число.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Возвращает выражение в виде процента (умноженное на 100) с символом % в конце.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Возвращает целое число, указывающее начальную позицию первого вхождения одной строки в другую.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Возвращает позицию первого вхождения одной строки в другую, начиная с правой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Возвращает строку, образуемую путем соединения нескольких подстрок, содержащихся в массиве.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Возвращает строку или символ, преобразованную в нижний регистр.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Возвращает строку, содержащую указанное число знаков с левой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Возвращает целое число, которое содержит число символов в строке.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Возвращает строку с выравниванием по левому краю, которая содержит указанную строку, приведенную к заданной длине.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Возвращает строку, содержащую копию указанной строки без начальных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Возвращает строку, содержащую указанное число символов из строки.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Возвращает строку, в которой указанная подстрока заменена другой подстрокой заданное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Возвращает строку, содержащую указанное число знаков с правой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Возвращает по правому краю строку, содержащую указанную строку, приведенную к заданной длине.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Возвращает строку, содержащую копию указанной строки без пробелов в конце.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Возвращает строку, состоящую из указанного числа пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Возвращает отсчитываемый от нуля одномерный массив, содержащий указанное число подстрок.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Возвращает значение -1, 0 или 1, в зависимости от результата сравнения строк.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Возвращает строку, преобразованную указанным образом.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Возвращает строку или объект, состоящий из указанного знака, повторенного указанное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Возвращает строку, в котором изменяется порядок следования символов в указанной строке.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Возвращает строку, содержащую копию указанной строки без начальных или конечных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Возвращает строку или символ, содержащий указанную строку, преобразованную в верхний регистр.|  
  
 Можно использовать [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) порядок, согласно языковому стандарту системы сортировки инструкции, чтобы указать режим сравнения строк с помощью текста без учета регистра (`Text`) или по внутренним двоичным представлениям знаков) `Binary`). Метод сравнения текста по умолчанию — `Binary`.  
  
## <a name="example"></a>Пример  
 В этом примере используется `UCase` функцию для возврата версии строки в верхнем регистре.  
  
 [!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `LTrim` функции, чтобы убрать пробелы в начале и `RTrim` функция, чтобы убрать конечные пробелы из строковой переменной. Она использует `Trim` функцию для удаления обоих типов пробелов.  
  
 [!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` функция возвращает указанное количество символов из строки.  
  
 [!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `Len` для возврата числа знаков в строке.  
  
 [!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example"></a>Пример  
 В этом примере используется `InStr` функцию для возврата позиции первого вхождения одной строки в другую.  
  
 [!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example"></a>Пример  
 В этом примере показаны различные способы использования `Format` функция для форматирования значений с помощью обоих `String` форматы и определенных пользователем форматов. В качестве разделителя даты (`/`), разделителя времени (`:`) и индикаторов AM/PM (`t` и `tt`), Фактическое отображение системой зависит от параметров языкового стандарта, используя код. Если времени и даты будут выводиться в среде разработки, используются краткий формат времени и даты региональных установок кода.  
  
> [!NOTE]
>  Для языков, использующих 24-часовом формате, индикаторы AM/PM (`t` и `tt`) не отображаются.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Члены библиотеки времени выполнения Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Сводка по работе со строками](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
