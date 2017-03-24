---
title: "Константы и перечисления (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
- constants
- constants, list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e37ef2e3c51e96e85cb214054195016e69d52382
ms.lasthandoff: 03/13/2017

---
# <a name="constants-and-enumerations-visual-basic"></a>Константы и перечисления (Visual Basic)
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет ряд предопределенных констант и перечислений для разработчиков. Константы хранят значения, которые остаются неизменными во время выполнения приложения. Перечисления предоставляют удобный способ работы с наборами связанных констант и связывания постоянных значений с именами.  
  
## <a name="constants"></a>Константы  
  
### <a name="conditional-compilation-constants"></a>Константы условной компиляции  
 В следующей таблице перечислены предопределенные константы, доступные для условной компиляции.  
  
|**Константа**|**Описание**|  
|---|---|  
|`CONFIG`|Строка, соответствующая текущей настройке **активная конфигурация решения** поле **Configuration Manager**.|  
|`DEBUG`|Объект `Boolean` значение, которое может быть задано в **свойства проекта** диалоговое окно. По умолчанию конфигурация отладки для проекта определяет `DEBUG`. При `DEBUG` определяется, <xref:System.Diagnostics.Debug>методы класса выводят **вывода** окно.</xref:System.Diagnostics.Debug> Если она не определена, <xref:System.Diagnostics.Debug>методы класса не компилируются и не формирует выходные данные отладки.</xref:System.Diagnostics.Debug>|  
|`TARGET`|Строка, представляющая тип выходных данных для проекта или параметр командной строки **/target-** параметр. Возможные значения `TARGET` являются:<br /><br /> -«winexe» для приложения Windows.<br />-«exe» для консольного приложения.<br />-«Библиотека» для библиотеки классов.<br />-«модуль» для модуля.<br />- **/Target-** может быть установлен [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] интегрированной среды разработки. Дополнительные сведения см. в разделе [/Target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Объект `Boolean` значение, которое может быть задано в **свойства проекта** диалоговое окно. По умолчанию все конфигурации для проекта определяют `TRACE`. При `TRACE` определяется, <xref:System.Diagnostics.Trace>методы класса выводят **вывода** окно.</xref:System.Diagnostics.Trace> Если она не определена, <xref:System.Diagnostics.Trace>класс, методы не компилируются и не `Trace` создаются выходные данные.</xref:System.Diagnostics.Trace>|  
|`VBC_VER`|Число, представляющее [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] версии в *основных*.* вспомогательные* формат. Номер версии для [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 8.0.|  
  
### <a name="print-and-display-constants"></a>Константы печати и отображения  
 При вызове печати и отобразить функции, можно использовать следующие константы в коде вместо фактических значений.  
  
|**Константа**|**Описание**|  
|---|---|  
|`vbCrLf`|Сочетание символов возврата каретки.|  
|`vbCr`|Символ возврата каретки.|  
|`vbLf`|Символ перевода строки.|  
|`vbNewLine`|Символ новой строки.|  
|`vbNullChar`|Символ NULL.|  
|`vbNullString`|Не отличается от строки нулевой длины (»»); используется для вызова внешних процедур.|  
|`vbObjectError`|Номер ошибки. Номера пользовательских ошибках должны быть больше, чем это значение. Пример:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Символ табуляции.|  
|`vbBack`|Символ возврата каретки.|  
|`vbFormFeed`|Не используется в Microsoft Windows.|  
|`vbVerticalTab`|Не удобно использовать в Microsoft Windows.|  
  
## <a name="enumerations"></a>Перечисления  
 В следующей таблице перечислены и описаны перечисления, предоставляемые [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
|Перечисление|Описание|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle></xref:Microsoft.VisualBasic.AppWinStyle>|Указывает стиль окна для использования вызванной программы при вызове <xref:Microsoft.VisualBasic.Interaction.Shell%2A>функция.</xref:Microsoft.VisualBasic.Interaction.Shell%2A>|  
|<xref:Microsoft.VisualBasic.AudioPlayMode></xref:Microsoft.VisualBasic.AudioPlayMode>|Указывает, как воспроизводить звуки при вызове методов воспроизведения.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole></xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Указывает тип роли для проверки при вызове <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>метода.</xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
|<xref:Microsoft.VisualBasic.CallType></xref:Microsoft.VisualBasic.CallType>|Указывает тип процедуры, вызываемой при вызове <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>функция.</xref:Microsoft.VisualBasic.Interaction.CallByName%2A>|  
|<xref:Microsoft.VisualBasic.CompareMethod></xref:Microsoft.VisualBasic.CompareMethod>|Указывает, как сравнивать строки, вызывая функции сравнения.|  
|<xref:Microsoft.VisualBasic.DateFormat></xref:Microsoft.VisualBasic.DateFormat>|Указывает, как отображать даты при вызове <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>функция.</xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|  
|<xref:Microsoft.VisualBasic.DateInterval></xref:Microsoft.VisualBasic.DateInterval>|Указывает способ определения и форматирования интервалов дат при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption></xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Указывает, какие действия должны выполняться, если удаляемый каталог содержит файлы или каталоги.|  
|<xref:Microsoft.VisualBasic.DueDate></xref:Microsoft.VisualBasic.DueDate>|Указывает, когда должны осуществляться платежи при вызове финансовых методов.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType></xref:Microsoft.VisualBasic.FileIO.FieldType>|Указывает ли текстовые поля являются разделителями или фиксированной ширины.|  
|<xref:Microsoft.VisualBasic.FileAttribute></xref:Microsoft.VisualBasic.FileAttribute>|Указывает, что атрибуты файла для использования при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek></xref:Microsoft.VisualBasic.FirstDayOfWeek>|Указывает первый день недели для использования при вызове функций работы с датами.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear></xref:Microsoft.VisualBasic.FirstWeekOfYear>|Указывает первую неделю года для использования при вызове функций работы с датами.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult></xref:Microsoft.VisualBasic.MsgBoxResult>|Указывает, какая кнопка была нажата в окне сообщения, возвращаемые <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>функция.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle></xref:Microsoft.VisualBasic.MsgBoxStyle>|Указывает, какие кнопки отображаются при вызове <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>функция.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.OpenAccess></xref:Microsoft.VisualBasic.OpenAccess>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenMode></xref:Microsoft.VisualBasic.OpenMode>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.OpenShare></xref:Microsoft.VisualBasic.OpenShare>|Указывает, как открыть файл при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption></xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Указывает, удален без возможности восстановления или поместить в корзине файл.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption></xref:Microsoft.VisualBasic.FileIO.SearchOption>|Указывает, следует ли выполнять поиск всех или только каталоги верхнего уровня.|  
|<xref:Microsoft.VisualBasic.TriState></xref:Microsoft.VisualBasic.TriState>|Указывает `Boolean` значение или должно ли использоваться значение по умолчанию при вызове функций форматирования чисел.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption></xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Указывает, что следует сделать, если пользователь нажимает кнопку **отменить** во время выполнения операции.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption></xref:Microsoft.VisualBasic.FileIO.UIOption>|Указывает, следует ли отображать диалоговое окно хода выполнения при копировании, удалении или перемещении файлов и каталогов.|  
|<xref:Microsoft.VisualBasic.VariantType></xref:Microsoft.VisualBasic.VariantType>|Указывает тип объекта variant, возвращенные <xref:Microsoft.VisualBasic.Information.VarType%2A>функция.</xref:Microsoft.VisualBasic.Information.VarType%2A>|  
|<xref:Microsoft.VisualBasic.VbStrConv></xref:Microsoft.VisualBasic.VbStrConv>|Указывает, какого типа преобразование необходимо выполнить при вызове <xref:Microsoft.VisualBasic.Strings.StrConv%2A>функция.</xref:Microsoft.VisualBasic.Strings.StrConv%2A>|  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Общие сведения о константах](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Общие сведения о перечислениях](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
