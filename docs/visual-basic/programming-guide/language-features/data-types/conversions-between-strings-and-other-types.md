---
title: "Преобразование значений между строковыми и другими типами (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "преобразования, тип данных"
  - "преобразования, тип"
  - "преобразование типов данных, строка"
  - "региональные параметры"
  - "преобразование строк"
  - "преобразование типов, строка"
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Преобразование значений между строковыми и другими типами (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Можно преобразовать числовые, `Boolean` или значения дата\/время в `String`.  Возможно также обратное преобразование — от строковых значений к числовым, `Boolean` или `Date` — с интерпретацией содержимого строки как значения, допустимого для конечного типа данных.  Если это невозможно, то возникает ошибка во временя выполнения.  
  
 Преобразования для всех этих присваиваний в том же направлении являются сужающими преобразованиями.  Следует использовать ключевые слова преобразования типов \(`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`\>, `CUInt`\>, `CULng`\>, `CUShort`\> и `CType`\>\).  Функции <xref:Microsoft.VisualBasic.Strings.Format%2A> и <xref:Microsoft.VisualBasic.Conversion.Val%2A> предоставляют дополнительные возможности управления преобразованием строк и чисел.  
  
 Если определены класс или структура, то можно определить операторы преобразования типов между `String` и типом класса или структуры.  Дополнительные сведения см. в разделе [Практическое руководство. Определение оператора преобразования](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## Преобразование чисел в строки  
 Функция `Format` позволяет преобразовать число в отформатированную строку, которая может включать не только соответствующие разряды, но и символы форматирования, например знак валюты \(`$`\), разделители тысяч или *разделители десятичных групп* \(например, пробел\) и десятичный разделитель \(`,`\)`.`\)  Функция `Format` автоматически использует соответствующие знаки, заданные в элементе **Язык и региональные стандарты Панели управления Windows**.  
  
 Следует учитывать, что оператор объединения \(`&`\) может преобразовать число в строку неявным образом, как показано в следующем примере:  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## Преобразование чисел в строки  
 Функция `Val` позволяет явным образом преобразовать цифры в строке в число.  Функция `Val` анализирует строку, пока не встретится знак, отличный от цифры, пробела, табуляции, разрыва строки или точки.  Сочетания "&O" и "&H" изменяют основание системы счисления и завершают считывание.  Пока не будет остановлено считывание, функция `Val` преобразует все соответствующие знаки в числовые значения.  Например, следующий оператор возвращает значение `141.825`:  
  
 `Val("   14   1.825 miles")`  
  
 При преобразовании строки в числовое значение [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] использует для интерпретации разделителя групп разрядов, разделителя дробной части и символа денежной единицы параметры, заданные в **Панели управления** Windows **Язык и региональные стандарты**.  Это означает, что преобразования при одних параметрах могут быть успешными, а при других — нет.  Например, `"$14.20"` приемлемо в англоязычной среде, но неприемлемо во франкоязычной.  
  
## См. также  
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Практическое руководство. Преобразование объекта к другому типу в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Знакомство с международными приложениями на платформе .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)