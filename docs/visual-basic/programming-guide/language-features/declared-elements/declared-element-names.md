---
title: Declared Element Names
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: e8620517b934a5f1a97ea25c5a94c8b932bb47b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345433"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="0afb4-102">Имена объявленных типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0afb4-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="0afb4-103">Каждый объявленный элемент имеет имя, также называемое *идентификатором*, которое используется кодом для ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="0afb4-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0afb4-104">Правила</span><span class="sxs-lookup"><span data-stu-id="0afb4-104">Rules</span></span>  
 <span data-ttu-id="0afb4-105">Имя элемента в Visual Basic должно соответствовать следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="0afb4-105">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="0afb4-106">Оно должно начинаться с буквы или знака подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="0afb4-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="0afb4-107">Оно должно содержать только буквы, цифры и знаки подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="0afb4-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="0afb4-108">Он должен содержать по крайней мере одну букву или цифру в десятичном формате, если начинается с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="0afb4-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="0afb4-109">Длина не должна превышать 1023 символов.</span><span class="sxs-lookup"><span data-stu-id="0afb4-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="0afb4-110">Ограничение длины в 1023 символов также применяется ко всей строке полного имени, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="0afb4-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="0afb4-111">В следующем примере показаны некоторые допустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="0afb4-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="0afb4-112">В следующем примере показаны некоторые недопустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="0afb4-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="0afb4-113">Первый содержит только символ подчеркивания, второй начинается с десятичной цифры, а третий содержит недопустимый символ ($).</span><span class="sxs-lookup"><span data-stu-id="0afb4-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="0afb4-114">Имена элементов, начинающиеся с символа подчеркивания (`_`), не являются частью [независимость от языка и независимых от языка компонентов](../../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимый код не может использовать компонент, определяющий такие имена.</span><span class="sxs-lookup"><span data-stu-id="0afb4-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="0afb4-115">Однако символ подчеркивания в любой другой должности в имени элемента является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="0afb4-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="0afb4-116">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="0afb4-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="0afb4-117">В качестве практического занятия имя должно быть как можно более коротким, а также четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="0afb4-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="0afb4-118">Это повышает удобочитаемость кода и сокращает длину строки и размер исходного файла.</span><span class="sxs-lookup"><span data-stu-id="0afb4-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="0afb4-119">С другой стороны, ваше имя не должно быть настолько коротким, что оно не имеет адекватного описания того, что представляет элемент и как код использует его.</span><span class="sxs-lookup"><span data-stu-id="0afb4-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="0afb4-120">Это важно для удобочитаемости кода.</span><span class="sxs-lookup"><span data-stu-id="0afb4-120">This is important for the readability of your code.</span></span> <span data-ttu-id="0afb4-121">Если кто-то другой пытается понять его, или если вы самостоятельно просматриваете его после написания, подходящие имена элементов могут сэкономить на значительном количестве времени.</span><span class="sxs-lookup"><span data-stu-id="0afb4-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="0afb4-122">Экранированные имена</span><span class="sxs-lookup"><span data-stu-id="0afb4-122">Escaped Names</span></span>  
 <span data-ttu-id="0afb4-123">Как правило, имя элемента не должно совпадать ни с одним из ключевых слов, зарезервированных Visual Basic, например `Case` или `Friend`.</span><span class="sxs-lookup"><span data-stu-id="0afb4-123">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="0afb4-124">Однако можно определить *escape-имя*, заключенное в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="0afb4-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="0afb4-125">Экранированное имя может соответствовать любому ключевому слову Visual Basic, так как квадратные скобки удаляют неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="0afb4-125">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="0afb4-126">Скобки также используются при ссылке на имя позже в коде.</span><span class="sxs-lookup"><span data-stu-id="0afb4-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="0afb4-127">Как правило, экранированные имена следует использовать только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="0afb4-127">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="0afb4-128">Код перенесен из предыдущей версии Visual Basic не зарезервированного ключевого слова, используемого в качестве имени; ни</span><span class="sxs-lookup"><span data-stu-id="0afb4-128">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="0afb4-129">Вы работаете с кодом, написанным на другом языке, на котором заданное ключевое слово не зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0afb4-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="0afb4-130">В противном случае следует рассмотреть возможность переименования элемента, если его имя конфликтует с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="0afb4-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="0afb4-131">Интегрированная среда разработки (IDE) предоставляет простой способ сделать это.</span><span class="sxs-lookup"><span data-stu-id="0afb4-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="0afb4-132">Дополнительные сведения см. в разделе [Рефакторинг](/visualstudio/ide/refactoring-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0afb4-132">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="0afb4-133">Чувствительность к регистру в именах</span><span class="sxs-lookup"><span data-stu-id="0afb4-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="0afb4-134">Имена элементов в Visual Basic не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="0afb4-134">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="0afb4-135">Это означает, что при сравнении двух имен, которые различаются только регистром букв, компилятор интерпретирует их как одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="0afb4-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="0afb4-136">Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.</span><span class="sxs-lookup"><span data-stu-id="0afb4-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="0afb4-137">Однако среда CLR использует привязку с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="0afb4-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="0afb4-138">Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет.</span><span class="sxs-lookup"><span data-stu-id="0afb4-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="0afb4-139">Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`.</span><span class="sxs-lookup"><span data-stu-id="0afb4-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="0afb4-140">Если впоследствии вы перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие ваш класс, больше не смогут получить доступ к этому элементу.</span><span class="sxs-lookup"><span data-stu-id="0afb4-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="0afb4-141">Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.</span><span class="sxs-lookup"><span data-stu-id="0afb4-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="0afb4-142">Имена и языковые стандарты</span><span class="sxs-lookup"><span data-stu-id="0afb4-142">Names and Locales</span></span>  
 <span data-ttu-id="0afb4-143">Сравнение имен не зависит от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="0afb4-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="0afb4-144">Если два имени совпадают в одном языковом стандарте, они гарантированно будут соответствовать всем языкам.</span><span class="sxs-lookup"><span data-stu-id="0afb4-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0afb4-145">См. также</span><span class="sxs-lookup"><span data-stu-id="0afb4-145">See also</span></span>

- [<span data-ttu-id="0afb4-146">Объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="0afb4-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [<span data-ttu-id="0afb4-147">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="0afb4-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="0afb4-148">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="0afb4-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="0afb4-149">Операторы</span><span class="sxs-lookup"><span data-stu-id="0afb4-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
