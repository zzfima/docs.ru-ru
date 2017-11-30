---
title: "Оператор Option Compare"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 281b18322f5be4e7dadcb9533680b25016a44c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="option-compare-statement"></a>Оператор Option Compare
Объявляет метод сравнения по умолчанию для использования при сравнении строковых данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`Binary`|Необязательно. Сравнения строк основываются на порядке сортировки, производном от внутренних двоичных представлений символов.<br /><br /> Такой тип сравнения наиболее часто применяется, если строки могут содержать символы, которые не следует интерпретировать как текст. В этом случае сравнение по алфавитной эквивалентности будет неверным (например, поскольку не будет учитываться регистр).|  
|`Text`|Необязательно. Результаты сравнения строк на основе сортировки текста без учета регистра определяются языком вашей системы.<br /><br /> Такой тип сравнения полезен, если строки содержат только текстовые символы, и нужно сравнить их с учетом алфавитной эквивалентности, то есть без учета регистра и  с учетом схожих букв. Например, можно считать `A` и `a` равными, а `Ä` и `ä` должны быть до `B` и `b`.|  
  
## <a name="remarks"></a>Примечания  
 Если используется оператор `Option Compare`, он должен быть указан в файле до всех прочих операторов.  
  
 Оператор `Option Compare` указывает метод сравнения строк (`Binary` или `Text`).  Метод сравнения текста по умолчанию — `Binary`.  
  
 Сравнение `Binary` сравнивает числовое значение Юникода каждого символа в каждой строке. Сравнение `Text` сравнивает каждый символ Юникода на основе его лексического значения в текущем языке.  
  
 В Microsoft Windows порядок сортировки определяется кодовой страницей. Дополнительные сведения см. в разделе [Кодовые страницы](/cpp/c-runtime-library/code-pages).  
  
 В следующем примере символы кодовой страницы ANSI 1252 сортируются с помощью оператора `Option Compare Binary`, создающего двоичный порядок сортировки.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Когда эти же символы этой же кодовой страницы сортируются с помощью `Option Compare Text`, получается следующий порядок сортировки текста.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a>Если оператор Option Compare отсутствует  
 Если исходный код не содержит `Option Compare` инструкции **Option Compare** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется. При использовании компилятора командной строки, заданные параметр [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) используется параметр компилятора.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a>Чтобы включить Option Compare в среде разработки  
  
1.  Выберите проект в **обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Задайте значение в **Option Compare** поле.  
  
 При создании проекта, **Option Compare** на **компиляции** набор вкладок **Option Compare** в **параметры** диалоговое окно. Чтобы изменить этот параметр, в **средства** меню, нажмите кнопку **параметры**. В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**. Начальный параметр по умолчанию в **VB значения по умолчанию** — **двоичных**.  
  
#### <a name="to-set-option-compare-on-the-command-line"></a>Чтобы включить Option Compare в командной строке  
  
-   Включить [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) параметра компилятора в **vbc** команды.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Option Compare` используется, чтобы задать двоичное сравнение в качестве метода сравнения строк по умолчанию. Чтобы использовать этот код, раскомментируйте оператор `Option Compare Binary` и поместите его в начало файла исходного кода.  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Option Compare` используется, чтобы задать сортировку текста без учета регистра в качестве метода сравнения строк по умолчанию. Чтобы использовать этот код, раскомментируйте оператор `Option Compare Text` и поместите его в начало файла исходного кода.  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>  
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Оператор Like](../../../visual-basic/language-reference/operators/like-operator.md)  
 [Строковые функции](../../../visual-basic/language-reference/functions/string-functions.md)  
 [Оператор Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
