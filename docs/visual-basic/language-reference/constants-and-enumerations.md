---
title: Константы и перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: 0a9c01269e12c2d84be4f30c236c439012a88153
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839595"
---
# <a name="constants-and-enumerations-visual-basic"></a>Константы и перечисления (Visual Basic)
Visual Basic предоставляет ряд предопределенных констант и перечислений для разработчиков. Константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.  
  
## <a name="constants"></a>Константы  
  
### <a name="conditional-compilation-constants"></a>Константы условной компиляции  
 В следующей таблице перечислены предопределенные константы, доступные для условной компиляции.  
  
|**Константа**|**Описание**|  
|---|---|  
|`CONFIG`|Строка, соответствующая текущей настройке **активная конфигурация решения** поле **Configuration Manager**.|  
|`DEBUG`|Объект `Boolean` значение, которое можно задать в **свойства проекта** диалоговое окно. По умолчанию конфигурация отладки для проекта определяет `DEBUG`. Когда `DEBUG` определен, <xref:System.Diagnostics.Debug> методы класса выводят информацию **выходные данные** окна. Если она не определена, <xref:System.Diagnostics.Debug> методы класса не компилируются и не формирует выходные данные отладки.|  
|`TARGET`|Строка, представляющая тип выходных данных для проекта или параметр командной строки **/target** параметр. Возможные значения `TARGET` являются:<br /><br /> -«winexe», для приложения Windows.<br />-«exe» для консольного приложения.<br />-«Библиотека» для библиотеки классов.<br />-«модуль» для модуля.<br />- **/Target** может быть установлен в среде разработки Visual Studio. Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Объект `Boolean` значение, которое можно задать в **свойства проекта** диалоговое окно. По умолчанию все конфигурации для проекта определяют `TRACE`. Когда `TRACE` определен, <xref:System.Diagnostics.Trace> методы класса выводят информацию **выходные данные** окна. Если она не определена, <xref:System.Diagnostics.Trace> класс, методы не компилируются и не `Trace` создаются выходные данные.|  
|`VBC_VER`|Число, представляющее версию Visual Basic, *основных*. *дополнительный номер* формат. Номер версии для [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] 8.0.|  
  
### <a name="print-and-display-constants"></a>Константы печати и отображения  
 При вызове печати и отображения функций, можно использовать следующие константы в коде вместо фактических значений.  
  
|**Константа**|**Описание**|  
|---|---|  
|`vbCrLf`|Сочетание символов возврата каретки.|  
|`vbCr`|Символ возврата каретки.|  
|`vbLf`|Символ перевода строки.|  
|`vbNewLine`|Символ новой строки.|  
|`vbNullChar`|Нуль-символ.|  
|`vbNullString`|Не так же, как строка нулевой длины (»»); используется для вызова внешних процедур.|  
|`vbObjectError`|Номер ошибки. Номера пользовательских ошибок должно быть больше, чем это значение. Пример:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Символ табуляции.|  
|`vbBack`|Символ возврата каретки.|  
|`vbFormFeed`|Не используется в Microsoft Windows.|  
|`vbVerticalTab`|Бесполезные в Microsoft Windows.|  
  
## <a name="enumerations"></a>Перечисления  
 В следующей таблице перечислены и описаны перечисления, предоставляемые Visual Basic.  
  
|Перечисление|Описание|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Указывает стиль окна для использования вызванной программы при вызове <xref:Microsoft.VisualBasic.Interaction.Shell%2A> функции.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Указывает, как воспроизводить звуки при вызове методов воспроизведения.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Указывает тип роли для проверки при вызове <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> метод.|  
|<xref:Microsoft.VisualBasic.CallType>|Указывает тип процедуры, вызываемой при вызове <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> функции.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Указывает способ сравнения строк, при вызове функций сравнения.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Указывает, как отображать даты при вызове <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> функции.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Указывает способ определения и форматирования интервалов дат при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Указывает, какие действия должны выполняться, если каталог, в который требуется удалить содержит файлы или каталоги.|  
|<xref:Microsoft.VisualBasic.DueDate>|Указывает, когда должны осуществляться платежи при вызове финансовых методов.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Указывает ли текстовые поля являются разделителями или фиксированной ширины.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Указывает атрибуты файла, для использования при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Указывает первый день недели для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Указывает первую неделю года для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Указывает, какая кнопка нажата в окне сообщения, возвращаемом функцией <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Указывает, какие кнопки отображаются при вызове функции <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Указывает, следует ли файл удален без возможности восстановления или помещен в корзину.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Указывает, следует ли выполнять поиск по всем или только каталоги верхнего уровня.|  
|<xref:Microsoft.VisualBasic.TriState>|Указывает `Boolean` значение или значение по умолчанию должно ли использоваться при вызове функций форматирования чисел.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Указывает, что должно быть выполнено, если пользователь нажимает кнопку **отменить** во время операции.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Указывает, следует ли отображать диалоговое окно хода выполнения при копировании, удалении или перемещении файлов или каталогов.|  
|<xref:Microsoft.VisualBasic.VariantType>|Указывает тип объекта variant, возвращенные <xref:Microsoft.VisualBasic.Information.VarType%2A> функции.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Указывает, преобразование какого типа следует выполнить при вызове функции <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>См. также

- [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)
- [Visual Basic](../../visual-basic/index.md)
- [Общие сведения о константах](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Общие сведения о перечислениях](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
