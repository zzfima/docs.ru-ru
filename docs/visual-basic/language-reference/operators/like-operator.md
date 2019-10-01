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
ms.openlocfilehash: 795ecc2e80d57af29ccd50c50d2dd209c6425e40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701132"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="7bb1b-102">Оператор Like (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bb1b-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="7bb1b-103">Сравнивает строку с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="7bb1b-104">В настоящее время оператор `Like` не поддерживается в проектах .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="7bb1b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bb1b-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="7bb1b-106">Части</span><span class="sxs-lookup"><span data-stu-id="7bb1b-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="7bb1b-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-107">Required.</span></span> <span data-ttu-id="7bb1b-108">Любая переменная `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-108">Any `Boolean` variable.</span></span> <span data-ttu-id="7bb1b-109">Результатом является значение `Boolean`, указывающее, удовлетворяет ли `string` `pattern`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="7bb1b-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-110">Required.</span></span> <span data-ttu-id="7bb1b-111">Произвольное выражение `String` .</span><span class="sxs-lookup"><span data-stu-id="7bb1b-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="7bb1b-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-112">Required.</span></span> <span data-ttu-id="7bb1b-113">Любое выражение `String`, удовлетворяющее соглашениям о соответствии шаблону, описанным в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="7bb1b-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bb1b-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bb1b-114">Remarks</span></span>  
 <span data-ttu-id="7bb1b-115">Если значение `string` соответствует шаблону, содержащемуся в `pattern`, `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="7bb1b-116">Если строка не соответствует шаблону, `result` имеет значение `False`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="7bb1b-117">Если оба `string` и `pattern` являются пустыми строками, результат будет `True`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="7bb1b-118">Метод сравнения</span><span class="sxs-lookup"><span data-stu-id="7bb1b-118">Comparison Method</span></span>  
 <span data-ttu-id="7bb1b-119">Поведение оператора `Like` зависит от [оператора Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7bb1b-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="7bb1b-120">По умолчанию для каждого исходного файла используется метод сравнения строк `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="7bb1b-121">Параметры шаблона</span><span class="sxs-lookup"><span data-stu-id="7bb1b-121">Pattern Options</span></span>  
 <span data-ttu-id="7bb1b-122">Встроенное сопоставление шаблонов предоставляет универсальное средство для сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="7bb1b-123">Функции сопоставления шаблонов позволяют сопоставить каждый символ в `string` с конкретным символом, подстановочным знаком, списком символов или диапазоном символов.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="7bb1b-124">В следующей таблице приведены символы, разрешенные в `pattern` и их совпадениях.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="7bb1b-125">Символов в `pattern`</span><span class="sxs-lookup"><span data-stu-id="7bb1b-125">Characters in `pattern`</span></span>|<span data-ttu-id="7bb1b-126">Совпадения в `string`</span><span class="sxs-lookup"><span data-stu-id="7bb1b-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="7bb1b-127">Любой отдельный знак</span><span class="sxs-lookup"><span data-stu-id="7bb1b-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="7bb1b-128">Ноль или более символов</span><span class="sxs-lookup"><span data-stu-id="7bb1b-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="7bb1b-129">Любая отдельная цифра (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="7bb1b-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="7bb1b-130">Любой отдельный символ в `charlist`</span><span class="sxs-lookup"><span data-stu-id="7bb1b-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="7bb1b-131">Любой отдельный символ, не являющийся `charlist`</span><span class="sxs-lookup"><span data-stu-id="7bb1b-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="7bb1b-132">Списки символов</span><span class="sxs-lookup"><span data-stu-id="7bb1b-132">Character Lists</span></span>  
 <span data-ttu-id="7bb1b-133">Группа из одного или нескольких символов (`charlist`), заключенных в квадратные скобки (`[ ]`), может использоваться для сопоставления любого отдельного символа в `string` и может содержать практически любой код символа, включая цифры.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="7bb1b-134">Восклицательный знак (`!`) в начале `charlist` означает, что сопоставление выполняется, если в `string` обнаружен любой символ, кроме символов в `charlist`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="7bb1b-135">При использовании вне квадратных скобок восклицательный знак соответствует самому себе.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="7bb1b-136">Специальные символы</span><span class="sxs-lookup"><span data-stu-id="7bb1b-136">Special Characters</span></span>  
 <span data-ttu-id="7bb1b-137">Чтобы найти соответствие с левой скобкой символов (`[`), знак вопроса (`?`), знак решетки (`#`) и звездочка (`*`), заключите их в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="7bb1b-138">Правая квадратная скобка (`]`) не может быть использована в группе для сопоставления самой себе, но ее можно использовать за пределами группы в качестве отдельного символа.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="7bb1b-139">Последовательность символов `[]` считается строкой нулевой длины (`""`).</span><span class="sxs-lookup"><span data-stu-id="7bb1b-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="7bb1b-140">Однако она не может входить в список символов, заключенный в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="7bb1b-141">Если вы хотите проверить, содержит ли значение `string` одну из групп символов или ни одного символа, можно дважды использовать `Like`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="7bb1b-142">Пример см. в статье [Практическое руководство. Сопоставление строки с шаблоном @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="7bb1b-143">Диапазоны символов</span><span class="sxs-lookup"><span data-stu-id="7bb1b-143">Character Ranges</span></span>  
 <span data-ttu-id="7bb1b-144">Используя дефис (`–`) для разделения нижней и верхней границ диапазона, `charlist` может указать диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="7bb1b-145">Например, `[A–Z]` приводит к совпадению, если соответствующая символьная позиции в `string` содержит любой символ в диапазоне `A` – `Z` и `[!H–L]` приводит к совпадению, если соответствующая символьная позиции содержит любой символ за пределами диапазон `H` — `L`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="7bb1b-146">При указании диапазона символов они должны отображаться в порядке сортировки по возрастанию, то есть от самого низкого до самого высокого.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="7bb1b-147">Таким образом, `[A–Z]` является допустимым шаблоном, но `[Z–A]` — нет.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="7bb1b-148">Несколько диапазонов символов</span><span class="sxs-lookup"><span data-stu-id="7bb1b-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="7bb1b-149">Чтобы указать несколько диапазонов для одной позиции символа, поместите их в одни и те же квадратные скобки без разделителей.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="7bb1b-150">Например, `[A–CX–Z]` приводит к совпадению, если соответствующая символьная позиции в `string` содержит любой символ в диапазоне `A` – `C` или диапазон `X` – `Z`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="7bb1b-151">Использование дефиса</span><span class="sxs-lookup"><span data-stu-id="7bb1b-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="7bb1b-152">Дефис (`–`) может располагаться в начале (после восклицательного знака, если есть) или в конце `charlist` для сопоставления с самим собой.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="7bb1b-153">В любом другом расположении дефис определяет диапазон символов, разделенных символами с любой стороны дефиса.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="7bb1b-154">Порядок сортировки</span><span class="sxs-lookup"><span data-stu-id="7bb1b-154">Collating Sequence</span></span>  
 <span data-ttu-id="7bb1b-155">Значение указанного диапазона зависит от порядка символов во время выполнения, как определено `Option Compare`, и параметра языкового стандарта системы, в которой выполняется код.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="7bb1b-156">Если `Option Compare Binary`, диапазон `[A–E]` соответствует `A`, `B`, `C`, `D` и `E`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="7bb1b-157">С `Option Compare Text`, `[A–E]` соответствует `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, 0, 1, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="7bb1b-158">Диапазон не соответствует `Ê` или `ê`, так как диакритические знаки сортируются после символов без диакритических знаков в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="7bb1b-159">Символы раскрутки</span><span class="sxs-lookup"><span data-stu-id="7bb1b-159">Digraph Characters</span></span>  
 <span data-ttu-id="7bb1b-160">В некоторых языках есть алфавитные символы, представляющие два отдельных символа.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="7bb1b-161">Например, несколько языков используют символ `æ` для представления символов `a` и `e`, когда они появляются вместе.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="7bb1b-162">Оператор `Like` распознает, что один символ отменяется и два отдельных символа эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="7bb1b-163">Если в параметрах национальной настройки системы задан язык, использующий символ относительных значений, то вхождение одного символа раскладки в `pattern` или `string` соответствует эквивалентной последовательности из двух символов в другой строке.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="7bb1b-164">Аналогично, символ отсчета в `pattern`, заключенный в квадратные скобки (сам по себе, в списке или в диапазоне), соответствует эквивалентной последовательности из двух символов в `string`.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7bb1b-165">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="7bb1b-165">Overloading</span></span>  
 <span data-ttu-id="7bb1b-166">Оператор `Like` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7bb1b-167">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7bb1b-168">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7bb1b-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb1b-169">Пример</span><span class="sxs-lookup"><span data-stu-id="7bb1b-169">Example</span></span>  
 <span data-ttu-id="7bb1b-170">В этом примере оператор `Like` используется для сравнения строк с различными шаблонами.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="7bb1b-171">Результаты попадают в переменную `Boolean`, указывающую, соответствует ли каждая строка шаблону.</span><span class="sxs-lookup"><span data-stu-id="7bb1b-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="7bb1b-172">См. также</span><span class="sxs-lookup"><span data-stu-id="7bb1b-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="7bb1b-173">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="7bb1b-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="7bb1b-174">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bb1b-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7bb1b-175">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="7bb1b-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7bb1b-176">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="7bb1b-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="7bb1b-177">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="7bb1b-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- <span data-ttu-id="7bb1b-178">[Практическое руководство. Сопоставление строки с шаблоном @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="7bb1b-178">[How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)</span></span>
