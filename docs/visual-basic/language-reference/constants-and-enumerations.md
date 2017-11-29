---
title: "Константы и перечисления (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fd298cc504f9e4faf5205e53ebbf2ee355a21b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="constants-and-enumerations-visual-basic"></a>Константы и перечисления (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]предоставляет ряд предопределенных констант и перечислений для разработчиков. Константы хранят значения, которые остаются неизменными во время выполнения приложения. Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.  
  
## <a name="constants"></a>Константы  
  
### <a name="conditional-compilation-constants"></a>Константы условной компиляции  
 В следующей таблице перечислены предопределенные константы, доступные для условной компиляции.  
  
|**Константа**|**Описание**|  
|---|---|  
|`CONFIG`|Строка, которая соответствует текущей настройке **активная конфигурация решения** поле **Configuration Manager**.|  
|`DEBUG`|Объект `Boolean` значение, которое может быть задано в **свойства проекта** диалоговое окно. По умолчанию конфигурация отладки для проекта определяет `DEBUG`. Когда `DEBUG` определен, <xref:System.Diagnostics.Debug> методы класса выводят информацию в **вывода** окна. Если она не определена, <xref:System.Diagnostics.Debug> методы класса не компилируются и не формирует выходные данные отладки.|  
|`TARGET`|Строка, представляющая тип выходных данных для проекта или параметр командной строки **/target-** параметр. Возможные значения `TARGET` являются:<br /><br /> -«winexe» для приложения Windows.<br />-«exe» для консольного приложения.<br />-«Библиотека» для библиотеки классов.<br />-«модуль» для модуля.<br />- **/Target-** может быть установлен [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] интегрированной среды разработки. Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Объект `Boolean` значение, которое может быть задано в **свойства проекта** диалоговое окно. По умолчанию все конфигурации для проекта определяют `TRACE`. Когда `TRACE` определен, <xref:System.Diagnostics.Trace> методы класса выводят информацию в **вывода** окна. Если она не определена, <xref:System.Diagnostics.Trace> класс, методы не компилируются и нет `Trace` создаются выходные данные.|  
|`VBC_VER`|Число, представляющее [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] версии в *основных*. *дополнительный номер* формат. Номер версии для [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] 8.0.|  
  
### <a name="print-and-display-constants"></a>Константы печати и отображения  
 При вызове печати и отобразить функции, можно использовать следующие константы в коде вместо фактических значений.  
  
|**Константа**|**Описание**|  
|---|---|  
|`vbCrLf`|Сочетание символов возврата каретки.|  
|`vbCr`|Символ возврата каретки.|  
|`vbLf`|Символ перевода строки.|  
|`vbNewLine`|Символ перевода строки.|  
|`vbNullChar`|Символ NULL.|  
|`vbNullString`|Не совпадает со значением строки нулевой длины (»»); используется для вызова внешних процедур.|  
|`vbObjectError`|Номер ошибки. Номера пользовательских ошибках должны быть больше, чем это значение. Пример:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Символ табуляции.|  
|`vbBack`|Символ возврата каретки.|  
|`vbFormFeed`|Не используется в Microsoft Windows.|  
|`vbVerticalTab`|Не используется в Microsoft Windows.|  
  
## <a name="enumerations"></a>Перечисления  
 В следующей таблице перечислены и описаны перечисления, предоставляемые [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
|Перечисление|Описание|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Указывает стиль окна для использования вызванной программы при вызове <xref:Microsoft.VisualBasic.Interaction.Shell%2A> функции.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Указывает, как воспроизводить звуки при вызове методов воспроизведения.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Указывает тип роли для проверки при вызове <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> метода.|  
|<xref:Microsoft.VisualBasic.CallType>|Указывает тип процедуры, вызываемой при вызове <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> функции.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Указывает, как сравнивать строки, вызывая функции сравнения.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Указывает способ отображения дат при вызове <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> функции.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Указывает способ определения и форматирования интервалов дат при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Указывает, какие действия должны выполняться, если каталог содержит файлы или каталоги.|  
|<xref:Microsoft.VisualBasic.DueDate>|Указывает, когда должны осуществляться платежи при вызове финансовых методов.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Указывает ли текстового поля с разделителями либо поле фиксированной длины.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Указывает атрибуты файла для использования при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Указывает первый день недели для использования при вызове функций работы с датами.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Указывает первую неделю года для использования при вызове функций работы с датами.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Указывает, какая кнопка нажата в окне сообщения, возвращаемом функцией <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Указывает, какие кнопки отображаются при вызове функции <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Определяет, удалены без возможности восстановления или поместить в корзине файл.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Указывает, следует ли выполнять поиск всех или только каталоги верхнего уровня.|  
|<xref:Microsoft.VisualBasic.TriState>|Указывает `Boolean` значение или должно ли использоваться значение по умолчанию при вызове функций форматирования чисел.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Указывает, что следует выполнить, если пользователь нажимает кнопку **отменить** во время выполнения операции.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Указывает, следует ли отображать диалоговое окно хода выполнения, когда копирование, удаление или перемещение файлов и каталогов.|  
|<xref:Microsoft.VisualBasic.VariantType>|Указывает тип объекта variant, возвращенные <xref:Microsoft.VisualBasic.Information.VarType%2A> функции.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Указывает, преобразование какого типа следует выполнить при вызове функции <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)  
 [Visual Basic](../../visual-basic/index.md)  
 [Общие сведения о константах](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Общие сведения о перечислениях](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
