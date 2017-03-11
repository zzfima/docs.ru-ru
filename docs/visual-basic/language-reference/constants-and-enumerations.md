---
title: "Константы и перечисления (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "константы"
  - "константы, список"
  - "перечисления [Visual Basic]"
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Константы и перечисления (Visual Basic)
[!INCLUDE[vs2017banner](../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет разработчикам ряд предопределенных констант и перечислений.  Константы содержат значения, которые остаются неизменными во время выполнения приложения.  Перечисления предлагают удобный способ работы с наборами связанных констант и присвоения постоянным значениям имен.  
  
## Константы  
  
### Константы условной компиляции  
 В следующей таблице перечислены предопределенные константы, доступные для условной компиляции.  
  
|||  
|-|-|  
|**Константа**|**Описание**|  
|`CONFIG`|Строка, соответствующая текущей настройке окна **Активная конфигурация решения** в **диспетчере конфигураций**.|  
|`DEBUG`|Значение `Boolean`, которое может устанавливаться в диалоговом окне **Свойства проекта**.  По умолчанию конфигурация отладки для проекта определяет `DEBUG`.  Если определена константа `DEBUG`, методы класса <xref:System.Diagnostics.Debug> производят вывод в окне **вывода**.  Если она не определена, то методы класса <xref:System.Diagnostics.Debug> не компилируются, и отладочный вывод не производится.|  
|`TARGET`|Строка, представляющая тип выходных данных для проекта или параметр **\/target** командной строки.  Возможные значения `TARGET`:<br /><br /> -   "winexe" для приложения Windows.<br />-   "exe" для консольного приложения.<br />-   "library" для библиотеки классов.<br />-   "module" для модуля.<br />-   Параметр **\/target** может быть установлен в [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)] интегрированной среде разработки.  Дополнительные сведения см. в разделе [\/target](../../visual-basic/reference/command-line-compiler/target.md).|  
|`TRACE`|Значение `Boolean`, которое может устанавливаться в диалоговом окне **Свойства проекта**.  По умолчанию все конфигурации для проекта определяют `TRACE`.  Если определена константа `TRACE`, методы класса <xref:System.Diagnostics.Trace> производят вывод в окне **вывода**.  Если она не определена, методы класса <xref:System.Diagnostics.Trace> не компилируются, и отладочный вывод `Trace` не производится.|  
|`VBC_VER`|Числовое значение, представляющее версию [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], в формате *основная*.*дополнительная*.  Номер версии [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] 8.0.|  
  
### Константы печати и отображения  
 При вызове функций печати и отображения можно использовать в коде следующие константы вместо указания реальных значений.  
  
|||  
|-|-|  
|**Константа**|**Описание**|  
|`vbCrLf`|Сочетание символов возврата каретки и перевода строки.|  
|`vbCr`|Символ возврата каретки.|  
|`vbLf`|Символ перевода строки.|  
|`vbNewLine`|Последовательность символов перехода на новую строку.|  
|`vbNullChar`|Символ NULL.|  
|`vbNullString`|Не аналогично пустой строке \(""\). Используется при вызове внешних процедур.|  
|`vbObjectError`|Номер ошибки.  Ошибки, определенные пользователем, должны иметь номер, превосходящий это число.  Примеры.<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|Символ табуляции.|  
|`vbBack`|Символ возврата каретки.|  
|`vbFormFeed`|Не используется в Microsoft Windows.|  
|`vbVerticalTab`|Не используется в Microsoft Windows.|  
  
## Перечисления  
 В следующей таблице перечислены и описаны перечисления, предоставляемые [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
|||  
|-|-|  
|Перечисление|Описание|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|Указывает стиль окна для использования вызванной программы при вызове функции <xref:Microsoft.VisualBasic.Interaction.Shell%2A>.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|Указывает, как воспроизводить звуки при вызове методов воспроизведения звуков.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|Указывает тип роли для проверки при вызове метода <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>.|  
|<xref:Microsoft.VisualBasic.CallType>|Указывает тип процедуры, вызываемой при вызове функции <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|Указывает, как сравнивать строки при вызове функций сравнения.|  
|<xref:Microsoft.VisualBasic.DateFormat>|Указывает, как отображать даты при вызове функции <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>.|  
|<xref:Microsoft.VisualBasic.DateInterval>|Указывает способ определения и форматирования интервалов дат при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|Указывает, какие действия должны выполняться, когда удаляемый каталог содержит файлы или каталоги.|  
|<xref:Microsoft.VisualBasic.DueDate>|Указывает, когда должны осуществляться платежи при вызове финансовых методов.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|Указывает тип текстовых полей: с разделителями или фиксированной ширины.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|Указывает атрибуты файла, используемые при вызове функций доступа к файлам.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|Указывает первый день недели для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|Указывает первую неделю года для использования при вызове функций для работы с датами.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|Указывает, какая кнопка была нажата в окне сообщения, возвращенного функцией <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|Указывает, какие кнопки отображаются при вызове функции <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.OpenMode>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.OpenShare>|Указывает, как открыть файл при вызове функций для работы с файлами.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|Указывает, следует ли удалить файл без возможности восстановления или поместить его в Корзину.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|Указывает, следует ли выполнять поиск по всем каталогам или только по каталогам верхнего уровня.|  
|<xref:Microsoft.VisualBasic.TriState>|Указывает логическое значение `Boolean` или должно ли использоваться значение по умолчанию при вызове функций форматирования чисел.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|Указывает, что необходимо сделать при нажатии пользователем кнопки **Отмена** во время операции.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|Указывает, следует ли отображать диалоговое окно хода выполнения при копировании, удалении и перемещении файлов и каталогов.|  
|<xref:Microsoft.VisualBasic.VariantType>|Указывает тип объекта Variant, возвращенного функцией <xref:Microsoft.VisualBasic.Information.VarType%2A>.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|Указывает, какого типа преобразование необходимо выполнить при вызове функции <xref:Microsoft.VisualBasic.Strings.StrConv%2A>.|  
  
## См. также  
 [Справочник по языку Visual Basic](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Общие сведения о константах](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Общие сведения о перечислениях](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)