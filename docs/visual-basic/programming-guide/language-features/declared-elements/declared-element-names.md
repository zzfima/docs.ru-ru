---
title: "Имена объявленных типов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22595eff2509d3954b3ce9d5038b19a681fbfbbe
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="030ae-102">Имена объявленных типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="030ae-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="030ae-103">Каждого объявленного элемента есть имя, также называемое *идентификатор*, которое используется код для ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="030ae-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="030ae-104">Правила</span><span class="sxs-lookup"><span data-stu-id="030ae-104">Rules</span></span>  
 <span data-ttu-id="030ae-105">Имя элемента в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] необходимо соблюдать следующие правила:</span><span class="sxs-lookup"><span data-stu-id="030ae-105">An element name in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="030ae-106">Оно должно начинаться с буквы или символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="030ae-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="030ae-107">Оно должно содержать только буквы, цифры и знаки подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="030ae-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="030ae-108">Оно должно содержать по крайней мере одну букву, цифру или десятичный знак, если он начинается со знака подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="030ae-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="030ae-109">Оно не должно быть более 1023 знаков.</span><span class="sxs-lookup"><span data-stu-id="030ae-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="030ae-110">Ограничение на длину 1023 знаков применяется также ко всей строке полное доменное имя, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="030ae-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="030ae-111">В следующем примере показано некоторые допустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="030ae-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="030ae-112">В следующем примере показано некоторые недопустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="030ae-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="030ae-113">Первый содержит только подчеркивания, второй начинается с десятичным и третий содержит недопустимый символ ($).</span><span class="sxs-lookup"><span data-stu-id="030ae-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="030ae-114">Имена элементов, начинающиеся с символа подчеркивания (`_`) которые не являются частью [независимость от языка и независимые от языка компоненты](../../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимом коде нельзя использовать компонент, определяющий такие имена.</span><span class="sxs-lookup"><span data-stu-id="030ae-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="030ae-115">Тем не менее символ подчеркивания в любом другом месте в имени элемента является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="030ae-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="030ae-116">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="030ae-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="030ae-117">На практике имя должно быть как можно более коротким при этом четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="030ae-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="030ae-118">Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.</span><span class="sxs-lookup"><span data-stu-id="030ae-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="030ae-119">С другой стороны на имя не должно быть настолько коротким, что он не описывает адекватно элемент представляет и как ваш код использует.</span><span class="sxs-lookup"><span data-stu-id="030ae-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="030ae-120">Это важно для удобства чтения кода.</span><span class="sxs-lookup"><span data-stu-id="030ae-120">This is important for the readability of your code.</span></span> <span data-ttu-id="030ae-121">Если кто пытается найти его, или вы сами вернетесь к нему длительное время после их создания, подходящие имена элементов можно сохранить значительное время.</span><span class="sxs-lookup"><span data-stu-id="030ae-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="030ae-122">Дублирующие имена</span><span class="sxs-lookup"><span data-stu-id="030ae-122">Escaped Names</span></span>  
 <span data-ttu-id="030ae-123">Как правило, имя элемента должно соответствует любые ключевые слова, зарезервированные [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], такие как `Case` или `Friend`.</span><span class="sxs-lookup"><span data-stu-id="030ae-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="030ae-124">Тем не менее, можно определить *escape-последовательность имя*, что заключено в квадратные скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="030ae-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="030ae-125">Escape-имя может совпадать с любым [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ключевое слово, так как любая неопределенность в скобки.</span><span class="sxs-lookup"><span data-stu-id="030ae-125">An escaped name can match any [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="030ae-126">Скобки также используются при обращении к имени в коде.</span><span class="sxs-lookup"><span data-stu-id="030ae-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="030ae-127">В общем случае следует использовать escape-имена только если:</span><span class="sxs-lookup"><span data-stu-id="030ae-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="030ae-128">Выполнена миграция кода из предыдущей версии [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не было зарезервировано ключевое слово, используемого в качестве имени; или</span><span class="sxs-lookup"><span data-stu-id="030ae-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="030ae-129">Работа с кодом, написанным на другом языке, в котором данное ключевое слово не резервируется.</span><span class="sxs-lookup"><span data-stu-id="030ae-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="030ae-130">В противном случае следует переименовать элемент, если его имя конфликтует с зарезервированным словом.</span><span class="sxs-lookup"><span data-stu-id="030ae-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="030ae-131">Интегрированной среды разработки (IDE) предоставляет простой способ сделать это.</span><span class="sxs-lookup"><span data-stu-id="030ae-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="030ae-132">Дополнительные сведения см. в разделе [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="030ae-132">For more information, see [Refactoring](/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="030ae-133">Учет регистра в именах</span><span class="sxs-lookup"><span data-stu-id="030ae-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="030ae-134">В именах элементов [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="030ae-134">Element names in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] are case-insensitive.</span></span> <span data-ttu-id="030ae-135">Это означает, что при сравнении двух имен, которые различаются только регистром букв, он интерпретирует их как тем же именем.</span><span class="sxs-lookup"><span data-stu-id="030ae-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="030ae-136">Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.</span><span class="sxs-lookup"><span data-stu-id="030ae-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="030ae-137">Однако общеязыковой среды выполнения (CLR) использует привязку с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="030ae-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="030ae-138">Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет.</span><span class="sxs-lookup"><span data-stu-id="030ae-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="030ae-139">Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`.</span><span class="sxs-lookup"><span data-stu-id="030ae-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="030ae-140">Если впоследствии перекомпилируете класс и измените имя элемента на `abc`, другие сборки, использующие больше не удалось получить доступ к этому элементу.</span><span class="sxs-lookup"><span data-stu-id="030ae-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="030ae-141">Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.</span><span class="sxs-lookup"><span data-stu-id="030ae-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="030ae-142">Имена и языковые стандарты</span><span class="sxs-lookup"><span data-stu-id="030ae-142">Names and Locales</span></span>  
 <span data-ttu-id="030ae-143">Сравнение имен не зависит от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="030ae-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="030ae-144">Если два имени совпадают в одном языке, они гарантированно совпадают во всех языковых стандартах.</span><span class="sxs-lookup"><span data-stu-id="030ae-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030ae-145">См. также</span><span class="sxs-lookup"><span data-stu-id="030ae-145">See Also</span></span>  
 [<span data-ttu-id="030ae-146">Объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="030ae-146">Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [<span data-ttu-id="030ae-147">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="030ae-147">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="030ae-148">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="030ae-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="030ae-149">Операторы</span><span class="sxs-lookup"><span data-stu-id="030ae-149">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
