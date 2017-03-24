---
title: "Тип данных Char (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Char"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "знак типа литерала С"
  - "Char - тип данных"
  - "Char - тип данных, знаковые литералы"
  - "типы данных [Visual Basic], назначение"
  - "символы типа литерала, C"
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Тип данных Char (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 16\-битовые \(2\-байтовые\) кодовые точки без знака со значениями в диапазоне от 0 до 65535.  Каждая *кодовая точка*, или код знака, представляет один символ Юникода.  
  
## Заметки  
 Тип данных `Char` используется при необходимости хранить только один символ, когда использовать `String` не требуется.  В некоторых случаях можно использовать `Char()`, массив элементов `Char`, для хранения нескольких знаков.  
  
 Значением по умолчанию `Char` является символ с кодом 0.  
  
## Знаки Юникода  
 Первые 128 кодовых точек \(от 0 до 127\) Юникода соответствуют буквам и символам стандартной американской  клавиатуры.  Эти первые 128 кодовых точек те же, что и в наборе знаков ASCII.  Следующие 128 кодовых точек \(от 128 до 255\) представляют специальные символы, например буквы, основанные на латинском алфавите, знаки ударения, символы валют и дроби.  Остальные кодовые комбинации \(256\-65535\) используются для широкого набора символов, включая международные текстовые знаки, диакритические знаки, математические и технические символы.  
  
 Можно использовать такие методы, как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> для определения классификации Юникод переменной `Char`.  
  
## Преобразования типов  
 Visual Basic не выполняет прямое преобразование между `Char` и числовыми типами.  Для преобразования значения `Char` в значение `Integer`, представляющее код символа, можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Asc%2A> или <xref:Microsoft.VisualBasic.Strings.AscW%2A>.  Для преобразования значения `Integer` в значение `Char` с таким кодом можно использовать функцию <xref:Microsoft.VisualBasic.Strings.Chr%2A> или <xref:Microsoft.VisualBasic.Strings.ChrW%2A>.  
  
 Если переключатель проверки типа \([Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)\) установлен, то необходимо добавить буквенный символ к односимвольному строковому литералу для определения его в качестве типа данных `Char`.  Это показано в приведенном ниже примере.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## Советы по программированию  
  
-   **Отрицательные числа.**  `Char` является беззнаковым типом и не может представлять отрицательные значения.  В любом случае не следует использовать переменные типа `Char` для хранения числовых значений.  
  
-   **Вопросы взаимодействия**. При построении интерфейса с компонентами, написанными не для .NET Framework, например автоматизации и COM\-объектов, следует помнить, что в других средах символьные типы имеют другой размер \(8 бит\).  Если такому компоненту передается 8\-разрядный аргумент, в новом коде Visual Basic объявите этот аргумент в качестве `Byte` вместо `Char`.  
  
-   **Расширение**. Тип данных `Char` может быть расширен до `String`.  Это означает, что можно преобразовать `Char` к `String` без возникновения ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении символа типа литерала `C` в конец односимвольного строкового литерала происходит приведение его к типу `Char`.   У `Char` нет символа типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Char?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Char?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)