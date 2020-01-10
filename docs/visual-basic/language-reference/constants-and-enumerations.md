---
title: Константы и перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 5109bf42c9caa7528c5405bb1a5cff0cfb62a5ac
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705760"
---
# <a name="constants-and-enumerations-visual-basic"></a>Константы и перечисления (Visual Basic)

Visual Basic предоставляет разработчикам ряд предопределенных констант и перечислений. Константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.  
  
## <a name="constants"></a>Константы  
  
### <a name="conditional-compilation-constants"></a>Константы условной компиляции  

 В следующей таблице перечислены стандартные константы, доступные для условной компиляции.  
  
|**Константа**|**Описание**|  
|---|---|  
|`CONFIG`|Строка, которая соответствует текущему значению поля **конфигурации активного решения** в **Configuration Manager**.|  
|`DEBUG`|Значение `Boolean`, которое может быть задано в диалоговом окне **Свойства проекта** . По умолчанию конфигурация отладки для проекта определяет `DEBUG`. При определении `DEBUG` методы класса <xref:System.Diagnostics.Debug> создают выходные данные в окне **вывода** . Если он не определен, <xref:System.Diagnostics.Debug> методы класса не компилируются и выходные данные отладки не создаются.|  
|`TARGET`|Строка, представляющая тип выходных данных для проекта или значение параметра командной строки для **целевого объекта** . Возможные значения `TARGET`:<br /><br /> — "winexe" для приложения Windows.<br />— "exe" для консольного приложения.<br />-"Library" для библиотеки классов.<br />— "Module" для модуля.<br />Параметр- **Target** можно задать в интегрированной среде разработки Visual Studio. Дополнительные сведения см. в разделе [-Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Значение `Boolean`, которое может быть задано в диалоговом окне **Свойства проекта** . По умолчанию все конфигурации проекта определяют `TRACE`. При определении `TRACE` методы класса <xref:System.Diagnostics.Trace> создают выходные данные в окне **вывода** . Если он не определен, <xref:System.Diagnostics.Trace> методы класса не компилируются и `Trace` выходные данные не создаются.|  
|`VBC_VER`|Число, представляющее Visual Basicную версию в *основном*. *дополнительный* формат.|  
  
### <a name="print-and-display-constants"></a>Константы печати и отображения  

 При вызове функций печати и отображения можно использовать в коде следующие константы вместо фактических значений.  
  
|**Константа**|**Описание**|  
|---|---|  
|`vbCrLf`|Сочетание символов возврата каретки и перевода строки.|  
|`vbCr`|Символ возврата каретки.|  
|`vbLf`|Символ перевода строки.|  
|`vbNewLine`|Символ новой строки.|  
|`vbNullChar`|Символ null.|  
|`vbNullString`|Не то же, что и строка нулевой длины (""); используется для вызова внешних процедур.|  
|`vbObjectError`|Номер ошибки. Ошибки, определенные пользователем, должны иметь номер, превосходящий это число. Например:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Символ табуляции.|  
|`vbBack`|Символ Backspace.|  
|`vbFormFeed`|Не используется в Microsoft Windows.|  
|`vbVerticalTab`|Не полезно в Microsoft Windows.|  
  
## <a name="enumerations"></a>Перечисления  

 В следующей таблице перечислены и описаны перечисления, предоставляемые Visual Basic.  
  
|Перечисление|Описание|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Указывает стиль окна для использования вызванной программы при вызове функции <xref:Microsoft.VisualBasic.Interaction.Shell%2A>.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Указывает, как воспроизводить звуки при вызове методов воспроизведения звуков.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Указывает тип роли для проверки при вызове метода <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>.|  
|<xref:Microsoft.VisualBasic.CallType>|Указывает тип процедуры, вызываемой при вызове функции <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Указывает, как сравнивать строки при вызове функций сравнения.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Указывает, как отображать даты при вызове функции <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Указывает способ определения и форматирования интервалов дат при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Указывает, какие действия должны выполняться, когда удаляемый каталог содержит файлы или каталоги.|  
|<xref:Microsoft.VisualBasic.DueDate>|Указывает, когда должны осуществляться платежи при вызове финансовых методов.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Указывает, являются ли текстовые поля разделителями или имеют фиксированную ширину.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Указывает атрибуты файла, используемые при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Указывает первый день недели для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Указывает первую неделю года для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Указывает, какая кнопка нажата в окне сообщения, возвращаемом функцией <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Указывает, какие кнопки отображаются при вызове функции <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Указывает, следует ли удалить файл без возможности восстановления или поместить в корзину.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Указывает, следует ли выполнять поиск по всем каталогам или только по каталогам верхнего уровня.|  
|<xref:Microsoft.VisualBasic.TriState>|Указывает на `Boolean` значение или следует ли использовать по умолчанию при вызове функций форматирования чисел.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Указывает, что следует делать, если пользователь нажимает кнопку **Отмена** во время операции.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Указывает, отображать ли диалоговое окно хода выполнения при копировании, удалении или перемещении файлов или каталогов.|  
|<xref:Microsoft.VisualBasic.VariantType>|Указывает тип объекта Variant, возвращенного функцией <xref:Microsoft.VisualBasic.Information.VarType%2A>.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Указывает, преобразование какого типа следует выполнить при вызове функции <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>См. также:

- [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)
- [Общие сведения о константах](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Общие сведения о перечислениях](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
