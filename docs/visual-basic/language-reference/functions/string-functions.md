---
title: Строковые функции (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 917797700c3e403971ce6f48174a282b1102f127
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799319"
---
# <a name="string-functions-visual-basic"></a>Строковые функции (Visual Basic)

В следующей таблице перечислены функции, которые Visual Basic предоставляет в <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> классе для поиска и работы со строками. Их можно рассматривать как Visual Basic встроенных функций; то есть вам не нужно вызывать их как явные члены класса, как показано в примерах. Дополнительные методы и в некоторых случаях дополняют методы, доступны в <xref:System.String?displayProperty=nameWithType> классе. 
  
|Метод .NET Framework|Описание|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|`Integer` Возвращает значение, представляющее код символа, соответствующий символу.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Возвращает символ, связанный с указанным кодом символа.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Возвращает массив с отсчетом от нуля, содержащий подмножество `String` массива на основе указанных условий фильтра.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Возвращает строку, отформатированную в соответствии с инструкциями `String` , содержащимися в выражении формата.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Возвращает выражение, отформатированное как денежное значение, используя символ валюты, определенный на панели управления системы.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Возвращает строковое выражение, представляющее значение даты и времени.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Возвращает выражение, отформатированное как число.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Возвращает выражение в виде процента (умноженное на 100) с символом % в конце.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Возвращает целое число, указывающее начальную точку первого вхождения одной строки в другую.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Возвращает расположение первого вхождения одной строки в другую, начиная с правой части строки.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Возвращает строку, созданную путем объединения нескольких подстрок, содержащихся в массиве.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Возвращает строку или символ, преобразованные в нижний регистр.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Возвращает строку, содержащую указанное число символов с левой стороны строки.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Возвращает целое число, содержащее количество символов в строке.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Возвращает строку с выравниванием влево, содержащую указанную строку, скорректированную до указанной длины.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Возвращает строку, содержащую копию указанной строки без начальных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Возвращает строку, содержащую указанное число символов из строки.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Возвращает строку, в которой указанная подстрока была заменена другой подстрокой указанное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Возвращает строку, содержащую указанное число символов от правой части строки.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Возвращает строку с выравниванием по правому краю, содержащую указанную строку, скорректированную до указанной длины.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Возвращает строку, содержащую копию указанной строки без конечных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Возвращает строку, состоящую из указанного числа пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Возвращает одномерный массив (с отсчетом от нуля), содержащий указанное число подстрок.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Возвращает-1, 0 или 1 на основе результата сравнения строк.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Возвращает строку, преобразованную указанным образом.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Возвращает строку или объект, состоящий из указанного символа, повторяемого указанное число раз.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Возвращает строку, в которой порядок символов в указанной строке изменяется на обратный.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Возвращает строку, содержащую копию указанной строки без начальных или конечных пробелов.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Возвращает строку или символ, содержащий указанную строку, преобразованную в верхний регистр.|  
  
 Можно использовать инструкцию [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) , чтобы задать, сравниваются ли строки с использованием порядка сортировки текста без учета регистра, определенного языковым стандартом системы`Text`() или внутренними двоичными представлениями символов (`Binary`). Метод сравнения текста по умолчанию — `Binary`.  
  
## <a name="example-ucase"></a>Пример UCase

В этом примере `UCase` функция возвращает версию строки в верхнем регистре.  
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example-ltrim"></a>Пример LTrim

В этом примере `LTrim` функция используется для удаления начальных пробелов `RTrim` и функции для удаления конечных пробелов из строковой переменной. Она использует `Trim` функцию для удаления обоих типов пробелов.  
  
[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example-mid"></a>Пример Mid

В этом примере `Mid` функция используется для возврата указанного числа символов из строки.  

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  

## <a name="example-len"></a>Пример Len

В этом примере `Len` функция возвращает количество символов в строке.  
  
[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example-instr"></a>Пример InStr

В этом примере `InStr` функция используется для возврата места первого вхождения одной строки в другую.  
  
[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example-format"></a>Пример Формат

В этом примере показаны различные способы применения `Format` функции для форматирования значений с использованием `String` обоих форматов и форматов, определяемых пользователем. Для`/`разделителя даты (), разделителя времени (`:`) и индикаторов AM/PM (`t` и `tt`) фактические отформатированные выходные данные, отображаемые системой, зависят от параметров языкового стандарта, используемых кодом. Если время и даты отображаются в среде разработки, используются короткий формат времени и короткий формат даты языкового стандарта кода.  
  
> [!NOTE]
> Для национальных настроек, в которых используется 24-часовой формат времени, индикаторы AM/PM`t` ( `tt`и) ничего не отображают.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Члены библиотеки времени выполнения Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Сводка по работе со строками](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [Методы класса System. String]<xref:System.String#methods?displayProperty=nameWithType>
