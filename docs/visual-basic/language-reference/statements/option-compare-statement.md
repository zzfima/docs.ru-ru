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
# <a name="option-compare-statement"></a><span data-ttu-id="3f7ce-102">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="3f7ce-102">Option Compare Statement</span></span>
<span data-ttu-id="3f7ce-103">Объявляет метод сравнения по умолчанию для использования при сравнении строковых данных.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f7ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f7ce-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="3f7ce-105">Части</span><span class="sxs-lookup"><span data-stu-id="3f7ce-105">Parts</span></span>  
  
|<span data-ttu-id="3f7ce-106">Термин</span><span class="sxs-lookup"><span data-stu-id="3f7ce-106">Term</span></span>|<span data-ttu-id="3f7ce-107">Определение</span><span class="sxs-lookup"><span data-stu-id="3f7ce-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="3f7ce-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-108">Optional.</span></span> <span data-ttu-id="3f7ce-109">Сравнения строк основываются на порядке сортировки, производном от внутренних двоичных представлений символов.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="3f7ce-110">Такой тип сравнения наиболее часто применяется, если строки могут содержать символы, которые не следует интерпретировать как текст.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="3f7ce-111">В этом случае сравнение по алфавитной эквивалентности будет неверным (например, поскольку не будет учитываться регистр).</span><span class="sxs-lookup"><span data-stu-id="3f7ce-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="3f7ce-112">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-112">Optional.</span></span> <span data-ttu-id="3f7ce-113">Результаты сравнения строк на основе сортировки текста без учета регистра определяются языком вашей системы.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="3f7ce-114">Такой тип сравнения полезен, если строки содержат только текстовые символы, и нужно сравнить их с учетом алфавитной эквивалентности, то есть без учета регистра и  с учетом схожих букв.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="3f7ce-115">Например, можно считать `A` и `a` равными, а `Ä` и `ä` должны быть до `B` и `b`.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f7ce-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f7ce-116">Remarks</span></span>  
 <span data-ttu-id="3f7ce-117">Если используется оператор `Option Compare`, он должен быть указан в файле до всех прочих операторов.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="3f7ce-118">Оператор `Option Compare` указывает метод сравнения строк (`Binary` или `Text`).</span><span class="sxs-lookup"><span data-stu-id="3f7ce-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="3f7ce-119">Метод сравнения текста по умолчанию — `Binary`.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="3f7ce-120">Сравнение `Binary` сравнивает числовое значение Юникода каждого символа в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="3f7ce-121">Сравнение `Text` сравнивает каждый символ Юникода на основе его лексического значения в текущем языке.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="3f7ce-122">В Microsoft Windows порядок сортировки определяется кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="3f7ce-123">Дополнительные сведения см. в разделе [Кодовые страницы](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="3f7ce-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="3f7ce-124">В следующем примере символы кодовой страницы ANSI 1252 сортируются с помощью оператора `Option Compare Binary`, создающего двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="3f7ce-125">Когда эти же символы этой же кодовой страницы сортируются с помощью `Option Compare Text`, получается следующий порядок сортировки текста.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="3f7ce-126">Если оператор Option Compare отсутствует</span><span class="sxs-lookup"><span data-stu-id="3f7ce-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="3f7ce-127">Если исходный код не содержит `Option Compare` инструкции **Option Compare** на [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) используется.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="3f7ce-128">При использовании компилятора командной строки, заданные параметр [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) используется параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="3f7ce-129">Чтобы включить Option Compare в среде разработки</span><span class="sxs-lookup"><span data-stu-id="3f7ce-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="3f7ce-130">Выберите проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="3f7ce-131">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3f7ce-132">Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="3f7ce-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="3f7ce-133">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="3f7ce-134">Задайте значение в **Option Compare** поле.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="3f7ce-135">При создании проекта, **Option Compare** на **компиляции** набор вкладок **Option Compare** в **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="3f7ce-136">Чтобы изменить этот параметр, в **средства** меню, нажмите кнопку **параметры**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="3f7ce-137">В **параметры** диалогового окна разверните **проекты и решения**, а затем нажмите кнопку **VB по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="3f7ce-138">Начальный параметр по умолчанию в **VB значения по умолчанию** — **двоичных**.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="3f7ce-139">Чтобы включить Option Compare в командной строке</span><span class="sxs-lookup"><span data-stu-id="3f7ce-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="3f7ce-140">Включить [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) параметра компилятора в **vbc** команды.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f7ce-141">Пример</span><span class="sxs-lookup"><span data-stu-id="3f7ce-141">Example</span></span>  
 <span data-ttu-id="3f7ce-142">В следующем примере оператор `Option Compare` используется, чтобы задать двоичное сравнение в качестве метода сравнения строк по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="3f7ce-143">Чтобы использовать этот код, раскомментируйте оператор `Option Compare Binary` и поместите его в начало файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3f7ce-144">Пример</span><span class="sxs-lookup"><span data-stu-id="3f7ce-144">Example</span></span>  
 <span data-ttu-id="3f7ce-145">В следующем примере оператор `Option Compare` используется, чтобы задать сортировку текста без учета регистра в качестве метода сравнения строк по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-145">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="3f7ce-146">Чтобы использовать этот код, раскомментируйте оператор `Option Compare Text` и поместите его в начало файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="3f7ce-146">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3f7ce-147">См. также</span><span class="sxs-lookup"><span data-stu-id="3f7ce-147">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>  
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="3f7ce-148">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="3f7ce-148">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="3f7ce-149">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="3f7ce-149">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="3f7ce-150">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f7ce-150">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="3f7ce-151">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="3f7ce-151">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="3f7ce-152">Строковые функции</span><span class="sxs-lookup"><span data-stu-id="3f7ce-152">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)  
 [<span data-ttu-id="3f7ce-153">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="3f7ce-153">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="3f7ce-154">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="3f7ce-154">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
