---
title: Оператор Option Compare
ms.date: 07/20/2015
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
ms.openlocfilehash: 675ad649650d9fbc6f2c0f1dc689aa682ca6103c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605307"
---
# <a name="option-compare-statement"></a><span data-ttu-id="b5b48-102">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="b5b48-102">Option Compare Statement</span></span>
<span data-ttu-id="b5b48-103">Объявляет метод сравнения по умолчанию для использования при сравнении строковых данных.</span><span class="sxs-lookup"><span data-stu-id="b5b48-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5b48-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="b5b48-105">Части</span><span class="sxs-lookup"><span data-stu-id="b5b48-105">Parts</span></span>  
  
|<span data-ttu-id="b5b48-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b5b48-106">Term</span></span>|<span data-ttu-id="b5b48-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b5b48-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="b5b48-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b5b48-108">Optional.</span></span> <span data-ttu-id="b5b48-109">Сравнения строк основываются на порядке сортировки, производном от внутренних двоичных представлений символов.</span><span class="sxs-lookup"><span data-stu-id="b5b48-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="b5b48-110">Такой тип сравнения наиболее часто применяется, если строки могут содержать символы, которые не следует интерпретировать как текст.</span><span class="sxs-lookup"><span data-stu-id="b5b48-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="b5b48-111">В этом случае сравнение по алфавитной эквивалентности будет неверным (например, поскольку не будет учитываться регистр).</span><span class="sxs-lookup"><span data-stu-id="b5b48-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="b5b48-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b5b48-112">Optional.</span></span> <span data-ttu-id="b5b48-113">Результаты сравнения строк на основе сортировки текста без учета регистра определяются языком вашей системы.</span><span class="sxs-lookup"><span data-stu-id="b5b48-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="b5b48-114">Такой тип сравнения полезен, если строки содержат только текстовые символы, и нужно сравнить их с учетом алфавитной эквивалентности, то есть без учета регистра и  с учетом схожих букв.</span><span class="sxs-lookup"><span data-stu-id="b5b48-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="b5b48-115">Например, можно считать `A` и `a` равными, а `Ä` и `ä` должны быть до `B` и `b`.</span><span class="sxs-lookup"><span data-stu-id="b5b48-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5b48-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5b48-116">Remarks</span></span>  
 <span data-ttu-id="b5b48-117">Если используется оператор `Option Compare`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="b5b48-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="b5b48-118">Оператор `Option Compare` указывает метод сравнения строк (`Binary` или `Text`).</span><span class="sxs-lookup"><span data-stu-id="b5b48-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="b5b48-119">Метод сравнения текста по умолчанию — `Binary`.</span><span class="sxs-lookup"><span data-stu-id="b5b48-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="b5b48-120">Сравнение `Binary` сравнивает числовое значение Юникода каждого символа в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="b5b48-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="b5b48-121">Сравнение `Text` сравнивает каждый символ Юникода на основе его лексического значения в текущем языке.</span><span class="sxs-lookup"><span data-stu-id="b5b48-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="b5b48-122">В Microsoft Windows порядок сортировки определяется кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="b5b48-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="b5b48-123">Дополнительные сведения см. в разделе [Кодовые страницы](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="b5b48-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="b5b48-124">В следующем примере символы кодовой страницы ANSI 1252 сортируются с помощью оператора `Option Compare Binary`, создающего двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="b5b48-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="b5b48-125">Когда эти же символы этой же кодовой страницы сортируются с помощью `Option Compare Text`, получается следующий порядок сортировки текста.</span><span class="sxs-lookup"><span data-stu-id="b5b48-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="b5b48-126">Если оператор Option Compare отсутствует</span><span class="sxs-lookup"><span data-stu-id="b5b48-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="b5b48-127">Если исходный код не содержит `Option Compare` инструкции **Option Compare** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="b5b48-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="b5b48-128">При использовании компилятора командной строки, заданные параметр [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="b5b48-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="b5b48-129">Чтобы включить Option Compare в среде разработки</span><span class="sxs-lookup"><span data-stu-id="b5b48-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="b5b48-130">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="b5b48-131">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-131">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b5b48-132">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-132">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="b5b48-133">Задайте значение в **Option Compare** поле.</span><span class="sxs-lookup"><span data-stu-id="b5b48-133">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="b5b48-134">При создании проекта, **Option Compare** на **компиляции** набор вкладок **Option Compare** в **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="b5b48-134">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="b5b48-135">Чтобы изменить этот параметр, в **средства** меню, нажмите кнопку **параметры**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-135">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="b5b48-136">В диалоговом окне **Параметры** разверните узел **Проекты и решения** и выберите пункт **Параметры Visual Basic по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-136">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="b5b48-137">Начальный параметр по умолчанию в **VB значения по умолчанию** — **двоичных**.</span><span class="sxs-lookup"><span data-stu-id="b5b48-137">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="b5b48-138">Чтобы включить Option Compare в командной строке</span><span class="sxs-lookup"><span data-stu-id="b5b48-138">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="b5b48-139">Включить [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) параметра компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="b5b48-139">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5b48-140">Пример</span><span class="sxs-lookup"><span data-stu-id="b5b48-140">Example</span></span>  
 <span data-ttu-id="b5b48-141">В следующем примере оператор `Option Compare` используется, чтобы задать двоичное сравнение в качестве метода сравнения строк по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5b48-141">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="b5b48-142">Чтобы использовать этот код, раскомментируйте оператор `Option Compare Binary` и поместите его в начало файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b5b48-142">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="b5b48-143">Пример</span><span class="sxs-lookup"><span data-stu-id="b5b48-143">Example</span></span>  
 <span data-ttu-id="b5b48-144">В следующем примере оператор `Option Compare` используется, чтобы задать сортировку текста без учета регистра в качестве метода сравнения строк по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5b48-144">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="b5b48-145">Чтобы использовать этот код, раскомментируйте оператор `Option Compare Text` и поместите его в начало файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b5b48-145">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b5b48-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b5b48-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>  
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="b5b48-147">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="b5b48-147">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="b5b48-148">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="b5b48-148">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="b5b48-149">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5b48-149">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="b5b48-150">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="b5b48-150">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="b5b48-151">Строковые функции</span><span class="sxs-lookup"><span data-stu-id="b5b48-151">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)  
 [<span data-ttu-id="b5b48-152">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="b5b48-152">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="b5b48-153">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="b5b48-153">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
