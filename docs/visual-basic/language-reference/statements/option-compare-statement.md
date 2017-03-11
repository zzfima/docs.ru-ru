---
title: "Оператор Option Compare | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Compare"
  - "vb.OptionCompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "двоичное сравнение"
  - "двоичное сравнение, Option Compare - оператор"
  - "Binary - ключевое слово, Option Compare - оператор"
  - "учет регистра, Option Compare - оператор"
  - "Compare - ключевое слово"
  - "Option Compare - оператор"
  - "сравнение строк [Visual Basic], Option Compare - оператор"
  - "сравнение строк [Visual Basic], сортировка данных"
  - "строки [Visual Basic], сравнение"
  - "строки [Visual Basic], возврат из функций"
  - "текст [Visual Basic], сравнение"
  - "Text - ключевое слово, Option Compare - оператор"
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Оператор Option Compare
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет метод сравнения по умолчанию для использования при сравнении строковых данных.  
  
## Синтаксис  
  
```  
Option Compare { Binary | Text }  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`Binary`|Необязательно.  Сравнения строк основываются на порядке сортировки, производном от внутренних двоичных представлений символов.<br /><br /> Такой тип сравнения наиболее часто применяется, если строки могут содержать символы, которые не следует интерпретировать как текст.  В этом случае сравнение по алфавитной эквивалентности будет неверным \(например, поскольку не будет учитываться регистр\).|  
|`Text`|Необязательно.  Результаты сравнения строк на основе сортировки текста без учета регистра определяются языком вашей системы.<br /><br /> Такой тип сравнения полезен, если строки содержат только текстовые символы, и нужно сравнить их с учетом алфавитной эквивалентности, то есть без учета регистра и  с учетом схожих букв.  Например, можно считать `A` и `a` равными, а `Ä` и `ä` должны быть до `B` и `b`.|  
  
## Заметки  
 Если используется оператор `Option Compare`, он должен быть указан в файле до всех прочих операторов.  
  
 Оператор `Option Compare` указывает метод сравнения строк \(`Binary` или `Text`\).  Метод сравнения текста по умолчанию — `Binary`.  
  
 Сравнение `Binary` сравнивает числовое значение Юникода каждого символа в каждой строке.  Сравнение `Text` сравнивает каждый символ Юникода на основе его лексического значения в текущем языке.  
  
 В Microsoft Windows порядок сортировки определяется кодовой страницей.  Для получения дополнительной информации см. [Кодовые страницы](/visual-cpp/c-runtime-library/code-pages).  
  
 В следующем примере символы кодовой страницы ANSI 1252 сортируются с помощью оператора `Option Compare Binary`, создающего двоичный порядок сортировки.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Когда эти же символы этой же кодовой страницы сортируются с помощью `Option Compare Text`, получается следующий порядок сортировки текста.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## Если оператор Option Compare отсутствует  
 Если исходный код не содержит оператор `Option Compare`, то используется параметр **Option Compare** в [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  Если используется компилятор командной строки, используется параметр компилятора [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
#### Чтобы включить Option Compare в среде разработки  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Для получения дополнительной информации см. [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/ru-ru/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в поле **Option Compare**.  
  
 При создании нового проекта значение параметра **Option Compare** на вкладке **Компиляция** задается в соответствии со значением параметра **Option Compare** в диалоговом окне **Настройки**.  Чтобы изменить этот параметр, в меню **Сервис** выберите **Настройки**.  В диалоговом окне **Настройки** разверните **Проекты и решения**, затем щелкните **Параметры Visual Basic по умолчанию**.  Начальный параметр по умолчанию в окне **Параметры Visual Basic по умолчанию** имеет значение **Двоичный**.  
  
#### Чтобы включить Option Compare в командной строке  
  
-   Включите параметр компилятора [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) в команду **vbc**.  
  
## Пример  
 В следующем примере оператор `Option Compare` используется, чтобы задать двоичное сравнение в качестве метода сравнения строк по умолчанию.  Чтобы использовать этот код, раскомментируйте оператор `Option Compare Binary` и поместите его в начало файла исходного кода.  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-compare-statement_1.vb)]  
  
## Пример  
 В следующем примере оператор `Option Compare` используется, чтобы задать сортировку текста без учета регистра в качестве метода сравнения строк по умолчанию.  Чтобы использовать этот код, раскомментируйте оператор `Option Compare Text` и поместите его в начало файла исходного кода.  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-compare-statement_2.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>   
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Строковые функции](../../../visual-basic/language-reference/functions/string-functions.md)   
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)