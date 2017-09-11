---
title: "Имена объявленных элементов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 899bcb2ecc8f5c07fdf4592e15827ff67f55c136
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="b0f9f-102">Имена объявленных типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0f9f-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="b0f9f-103">У каждого объявленного элемента есть имя, также называемое *идентификатор*, которое используется код для ссылки на него.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b0f9f-104">Правила</span><span class="sxs-lookup"><span data-stu-id="b0f9f-104">Rules</span></span>  
 <span data-ttu-id="b0f9f-105">Имя элемента в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] необходимо соблюдать следующие правила:</span><span class="sxs-lookup"><span data-stu-id="b0f9f-105">An element name in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="b0f9f-106">Оно должно начинаться с буквы или символа подчеркивания (`_`).</span><span class="sxs-lookup"><span data-stu-id="b0f9f-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="b0f9f-107">Оно должно содержать только буквенные символы, десятичные цифры и знаки подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="b0f9f-108">Он должен содержать по крайней мере один символ латинского алфавита или десятичной цифрой, если оно начинается со знака подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="b0f9f-109">Оно не должно быть более 1023 знаков.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="b0f9f-110">Ограничение на длину 1023 знаков применяется также ко всей строке полного имени, например `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="b0f9f-111">В следующем примере показано некоторые допустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="b0f9f-112">В следующем примере показано некоторые недопустимые имена элементов.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="b0f9f-113">Первый содержит только подчеркивания, второй начинается с десятичной цифры и третий содержит недопустимый символ ($).</span><span class="sxs-lookup"><span data-stu-id="b0f9f-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="b0f9f-114">Имена элементов, начинающиеся со знака подчеркивания (`_`) не являются частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), поэтому в CLS-совместимом коде нельзя использовать компонент, определяющий такие имена.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="b0f9f-115">Тем не менее символа подчеркивания в любом другом месте в имени элемента является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="b0f9f-116">Рекомендации по длине имени</span><span class="sxs-lookup"><span data-stu-id="b0f9f-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="b0f9f-117">На практике имя должно быть как можно более короткими при этом четко определять природу элемента.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="b0f9f-118">Это улучшает читаемость кода и уменьшает размер строки длины и исходный файл.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="b0f9f-119">С другой стороны имя необходимо настолько коротким, что оно неадекватно описывает элемент представляет и как код использует его.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="b0f9f-120">Это важно для удобства чтения кода.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-120">This is important for the readability of your code.</span></span> <span data-ttu-id="b0f9f-121">Если кто-то еще пытается разобраться, или вы сами вернетесь к нему длительное время после написания, подходящие имена элементов можно сохранить значительное время.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="b0f9f-122">Дублирующие имена</span><span class="sxs-lookup"><span data-stu-id="b0f9f-122">Escaped Names</span></span>  
 <span data-ttu-id="b0f9f-123">Как правило, имя элемента должно соответствует любое из ключевых слов, зарезервированных в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], такие как `Case` или `Friend`.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="b0f9f-124">Тем не менее, можно определить *escape-последовательность имя*, что заключено в скобки (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="b0f9f-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="b0f9f-125">Escape-имя может совпадать с любым [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ключевое слово, так как скобки исключают неопределенность.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-125">An escaped name can match any [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="b0f9f-126">Скобки также используются при обращении к этому имени в коде.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="b0f9f-127">В общем случае следует использовать escape-имена только если:</span><span class="sxs-lookup"><span data-stu-id="b0f9f-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="b0f9f-128">Выполнена миграция кода из предыдущей версии [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не было зарезервировано ключевое слово используемое в качестве имени; или</span><span class="sxs-lookup"><span data-stu-id="b0f9f-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="b0f9f-129">Работа с кодом, написанным на другом языке, в котором заданное ключевое слово не зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="b0f9f-130">В противном случае следует переименовать элемент, если его имя конфликтует с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="b0f9f-131">Интегрированную среду разработки (IDE) предоставляет простой способ сделать это.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="b0f9f-132">Дополнительные сведения см. в разделе [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span><span class="sxs-lookup"><span data-stu-id="b0f9f-132">For more information, see [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="b0f9f-133">Учет регистра в именах</span><span class="sxs-lookup"><span data-stu-id="b0f9f-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="b0f9f-134">В именах элементов [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-134">Element names in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] are case-insensitive.</span></span> <span data-ttu-id="b0f9f-135">Это означает, что при сравнении двух имен, которые различаются только регистром буквенных символов, компилятор воспринимает их как тем же именем.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="b0f9f-136">Например, он считает, что `ABC` и `abc` являются одним и тем же объявленным элементом.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="b0f9f-137">Однако общеязыковая среда выполнения (CLR) использует привязку с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="b0f9f-138">Таким образом, при создании сборки или DLL и предоставлении к ней доступа другим сборкам, в именах регистр учитываться не будет.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="b0f9f-139">Например, если определен класс с элементом `ABC`и другие сборки используют класс с помощью среды CLR, они должны ссылаться на элемент как на `ABC`.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="b0f9f-140">Если впоследствии перекомпиляции класса и измените имя элемента на `abc`, другие сборки, использующие больше не удалось получить доступ к этому элементу.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="b0f9f-141">Таким образом, при выпуске обновленной версии сборки нельзя изменять регистр имен открытых элементов.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="b0f9f-142">Имена и языковые стандарты</span><span class="sxs-lookup"><span data-stu-id="b0f9f-142">Names and Locales</span></span>  
 <span data-ttu-id="b0f9f-143">Сравнение имен не зависит от языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="b0f9f-144">Если два имени совпадают в одном языке, они гарантированно совпадают во всех языковых стандартах.</span><span class="sxs-lookup"><span data-stu-id="b0f9f-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f9f-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b0f9f-145">See Also</span></span>  
 <span data-ttu-id="b0f9f-146">[Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0f9f-146">[Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span></span>  
<span data-ttu-id="b0f9f-147"> [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="b0f9f-147"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="b0f9f-148"> [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="b0f9f-148"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="b0f9f-149"> [Операторы](../../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="b0f9f-149"> [Statements](../../../../visual-basic/language-reference/statements/index.md)</span></span>
