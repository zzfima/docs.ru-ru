---
title: Основы работы со строками
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 7141966e3c8a8cbce42111c56a85a00709e8fe1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344282"
---
# <a name="string-basics-in-visual-basic"></a>Основы работы со строками в Visual Basic
Тип данных `String` представляет последовательность символов (каждый из которых, в свою очередь, представляет экземпляр типа данных `Char`). This topic introduces the basic concepts of strings in Visual Basic.  
  
## <a name="string-variables"></a>Строковые переменные  
 Экземпляру строки можно назначить литеральное значение, которое представляет ряд символов. Пример:  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 Переменная `String` также может принимать любое выражение, результатом которого является строка. Ниже приведены примеры.  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 Любой литерал, который присваивается переменной `String`, должен быть заключен в кавычки (""). Это означает, что кавычки в пределах строки не могут быть представлены кавычкой. Например, следующий код вызовет ошибку компиляции:  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 Этот код вызывает ошибку, так как компилятор завершает строку после второй пары кавычек, а остаток строки интерпретируется как код. To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string. В следующем примере показан правильный способ указания кавычек в строке:  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 В предыдущем примере два символа кавычек перед словом `Look` становятся одним символом кавычек в строке. Три символа кавычек в конце строки представляют один символ кавычек в строке и конечный символ строки.  
  
 Строковые литералы могут содержать несколько строк:  
  
```vb  
Dim x = "hello  
world"  
```  
  
 Результирующая строка содержит последовательности новых строк, используемых в строковом литерале (vbcr, vbcrlf и т. д.).  Вам больше не требуется использовать старое решение:  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a>Символы в строках  
 Строку можно представить как последовательность значений `Char`. При этом тип `String` имеет встроенные функции, которые позволяют работать со строками, как с массивами. Like all array in .NET Framework, these are zero-based arrays. К определенному символу в строке можно обратиться с помощью свойства `Chars`, которое предоставляет механизм доступа к символу по позиции, в которой он отображается в строке. Пример:  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 В приведенном выше примере свойство `Chars` строки возвращает четвертый символ в строке, `D`, и присваивает его `myChar`. Вы также можете получить длину определенной строки с помощью свойства `Length`. Если вам требуется выполнить несколько манипуляций со строкой, можно преобразовать ее в массив экземпляров `Char` с помощью функции `ToCharArray` строки. Пример:  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 Переменная `myArray` теперь содержит массив значений `Char`, каждое из которых представляет символ из `myString`.  
  
## <a name="the-immutability-of-strings"></a>Неизменность строк  
 A string is *immutable*, which means its value cannot be changed once it has been created. Однако это не мешает назначить строковой переменной более одного значения. Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 Здесь строковая переменная создается, получает значение, которое затем изменяется.  
  
 В частности, в первой строке создается экземпляр типа `String`, которому присваивается значение `This string is immutable`. Во второй строке примера создается новый экземпляр, которому присваивается значение `Or is it?`. При этом строковая переменная удаляет ссылку на первый экземпляр и сохраняет ссылку на новый экземпляр.  
  
 В отличие от других встроенных типов данных `String` — это ссылочный тип. Если переменная ссылочного типа передается в качестве аргумента функции или подпрограмме, вместо фактического значения строки передается ссылка на адрес в памяти, где хранятся данные. Поэтому в предыдущем примере имя переменной остается таким же, но оно указывает на другой экземпляр класса `String`, который содержит новое значение.  
  
## <a name="see-also"></a>См. также

- [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Тип данных Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Базовые операции со строками в .NET Framework](../../../../standard/base-types/basic-string-operations.md)
