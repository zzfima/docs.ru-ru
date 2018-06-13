---
title: Оператор Like (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: a9c672a397510c69c9ee67358689feff80d8831a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605424"
---
# <a name="like-operator-visual-basic"></a>Оператор Like (Visual Basic)
Сравнивает строку с шаблоном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любой `Boolean` переменной. В результате `Boolean` значение, указывающее, ли `string` удовлетворяет `pattern`.  
  
 `string`  
 Обязательно. Произвольное выражение `String`.  
  
 `pattern`  
 Обязательно. Любой `String` выражения, согласующееся с правилами соответствия шаблону описано в разделе «Примечания».  
  
## <a name="remarks"></a>Примечания  
 Если значение в `string` соответствует шаблону в `pattern`, `result` — `True`. Если строка не удовлетворяет шаблон `result` — `False`. Если оба `string` и `pattern` являются пустыми строками, в результате `True`.  
  
## <a name="comparison-method"></a>Метод сравнения  
 Поведение `Like` зависит от оператора [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md). Метод сравнения строк по умолчанию для каждого исходного файла является `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Параметры шаблона  
 Сопоставление встроенных шаблонов представляет собой универсальный инструмент для сравнения строк. Средства подбора шаблона позволяют сопоставлять каждый символ в `string` определенный символ, подстановочный знак, список символ или диапазон символов. В следующей таблице показаны допустимые символы в `pattern` и их соответствия.  
  
|Символы в `pattern`|По условию поиска `string`|  
|-----------------------------|-------------------------|  
|`?`|Любой отдельный знак|  
|`*`|Ноль или более символов|  
|`#`|Любая отдельная цифра (0 – 9)|  
|`[charlist]`|Любой символ в `charlist`|  
|`[!charlist]`|Любой знак не в `charlist`|  
  
## <a name="character-lists"></a>Список знаков  
 Группа из одного или нескольких символов (`charlist`) заключена в квадратные скобки (`[ ]`) может использоваться для соответствует любому одиночному символу в `string` и может включать практически любой код символа, включая цифр.  
  
 Восклицательный знак (`!`) в начале `charlist` означает, что соответствие выполняются, если любой символ, кроме символов в `charlist` находится в `string`. При использовании вне скобок восклицательный знак соответствует самому себе.  
  
## <a name="special-characters"></a>Специальные символы  
 Для сопоставления левой скобки специальные символы (`[`), вопросительный знак (`?`), знак номера (`#`) и звездочка (`*`), заключите их в скобки. Закрывающая квадратная скобка (`]`) нельзя использовать в группе для сопоставления с самим собой, но он может использоваться за пределами группы как отдельный символ.  
  
 Последовательность символов `[]` считается строкой нулевой длины (`""`). Однако он не может быть частью список символов, заключенный в квадратные скобки. Если требуется проверить, является ли позиция в `string` содержит одну группу символов или вообще ни один знак, можно использовать `Like` дважды. Пример см. в разделе [как: сравнение строки на соответствие шаблону](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Диапазоны знаков  
 С помощью дефиса (`–`) для разделения нижней и верхней границы диапазона `charlist` можно указать диапазон символов. Например `[A–Z]` приводит к совпадению, если соответствующий символ поместите в `string` содержит любой знак в пределах диапазона `A`—`Z`, и `[!H–L]` приводит к совпадению, если соответствующий символ позиции любые символы вне диапазона `H`—`L`.  
  
 При указании диапазона символов, они должны располагаться в порядке возрастания, то есть, от меньшего к большему. Таким образом `[A–Z]` является допустимым шаблоном, но `[Z–A]` не является.  
  
### <a name="multiple-character-ranges"></a>Несколько символьных диапазонов  
 Чтобы указать несколько диапазонов для одной позиции символа, поместите их в одни квадратные скобки без разделителей. Например `[A–CX–Z]` приводит к совпадению, если соответствующий символ поместите в `string` содержит любой знак в любом диапазоне `A`—`C` или диапазон `X`—`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Использование дефиса  
 Дефис (`–`) могут отображаться в начале (после восклицательный знак, если таковые имеются) или в конце `charlist` для сопоставления с самим собой. В любом другом месте дефис обозначает диапазон символов, ограниченный знаками по обе стороны от дефиса.  
  
## <a name="collating-sequence"></a>Порядок сортировки  
 Значение указанного диапазона зависит от порядка во время выполнения, что определяется знаков `Option``Compare` и локали системы выполняется код. С `Option``Compare``Binary`, диапазон `[A–E]` соответствует `A`, `B`, `C`, `D`, и `E`. С `Option``Compare``Text`, `[A–E]` соответствует `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, и `e`. Диапазон не соответствует `Ê` или `ê` так, как диакритические знаки сортируются после стандартных в порядке сортировки.  
  
## <a name="digraph-characters"></a>Знаки диграфы  
 В некоторых языках существуют буквенные символы, которые представляют два отдельных знака. Например, несколько языков использовать символ `æ` для представления символов `a` и `e` при отображении друг с другом. `Like` Оператор распознает, что один диграф и два отдельных знака эквивалентны.  
  
 Если язык, который используется диграф указан в параметрах языкового стандарта системы, возникновение один диграф в любом `pattern` или `string` соответствует равнозначной последовательности двух знаков в другой строке. Аналогичным образом диграф в `pattern` заключена в квадратные скобки (сам по себе, в списке или в диапазоне) соответствует равнозначной последовательности двух знаков в `string`.  
  
## <a name="overloading"></a>Перегрузка  
 `Like` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры. Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное. Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется `Like` оператор для сравнения строк с различными шаблонами. Результаты переходят в `Boolean` переменной, указывающее, удовлетворяет ли каждая строка шаблону.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [Операторы сравнения](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Практическое руководство. Сравнение строки на соответствие с шаблоном](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
