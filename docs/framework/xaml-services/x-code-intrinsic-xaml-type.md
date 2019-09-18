---
title: Встроенный тип XAML x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053795"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="77233-102">Встроенный тип XAML x:Code</span><span class="sxs-lookup"><span data-stu-id="77233-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="77233-103">Позволяет размещать код в рабочей среде XAML.</span><span class="sxs-lookup"><span data-stu-id="77233-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="77233-104">Такой код может компилироваться любой реализацией процессора XAML, которая компилирует XAML, или оставлена в производстве XAML для последующего использования, например интерпретации средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="77233-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="77233-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="77233-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="77233-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="77233-106">Remarks</span></span>  
 <span data-ttu-id="77233-107">Код в `x:Code` элементе директивы XAML по-прежнему интерпретируется в общем пространстве имен XML и предоставленных пространствах имен XAML.</span><span class="sxs-lookup"><span data-stu-id="77233-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="77233-108">Таким образом, обычно необходимо заключить код, используемый для `x:Code` `CDATA` внутри сегмента.</span><span class="sxs-lookup"><span data-stu-id="77233-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="77233-109">`x:Code`не разрешено для всех возможных механизмов развертывания в рабочей среде XAML.</span><span class="sxs-lookup"><span data-stu-id="77233-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="77233-110">В конкретных платформах (например, WPF) код должен быть скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="77233-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="77233-111">В других платформах `x:Code` использование может вообще не допускаться.</span><span class="sxs-lookup"><span data-stu-id="77233-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="77233-112">Для платформ, допускающих управляемое `x:Code` содержимое, правильный компилятор `x:Code` языка для содержимого определяется параметрами и целевыми объектами содержащего проекта, который используется для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="77233-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="77233-113">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="77233-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="77233-114">Код, объявленный в `x:Code` для WPF, имеет несколько важных ограничений:</span><span class="sxs-lookup"><span data-stu-id="77233-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="77233-115">Элемент `x:Code` директивы должен быть непосредственным дочерним элементом корневого элемента в производстве XAML.</span><span class="sxs-lookup"><span data-stu-id="77233-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="77233-116">в родительском корневом элементе необходимо указать [директиву x:Class](x-class-directive.md) .</span><span class="sxs-lookup"><span data-stu-id="77233-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="77233-117">Код, помещенный `x:Code` в, будет обрабатываться компиляцией в пределах области разделяемого класса, который уже создается для этой страницы XAML.</span><span class="sxs-lookup"><span data-stu-id="77233-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="77233-118">Поэтому весь определенный код должен быть членом или переменными этого разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="77233-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="77233-119">Нельзя определить дополнительные классы, кроме вложенного класса в разделяемый класс (вложение разрешено, но это нетипично, так как на языке XAML нельзя ссылаться на вложенные классы).</span><span class="sxs-lookup"><span data-stu-id="77233-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="77233-120">Пространства имен CLR, отличные от пространства имен, используемого для существующего разделяемого класса, не могут быть определены или добавлены в.</span><span class="sxs-lookup"><span data-stu-id="77233-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="77233-121">Ссылки на сущности кода вне пространства имен CLR разделяемого класса должны быть полностью полными.</span><span class="sxs-lookup"><span data-stu-id="77233-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="77233-122">Если объявляемые члены являются переопределениями для переопределяемых членов разделяемого класса, это необходимо указать с помощью ключевого слова переопределения, зависящего от языка.</span><span class="sxs-lookup"><span data-stu-id="77233-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="77233-123">Если члены, объявленные в `x:Code` области, конфликтуют с членами разделяемого класса, созданного из XAML, таким образом, что компилятор сообщает о конфликте, файл XAML не может компилироваться или загружаться.</span><span class="sxs-lookup"><span data-stu-id="77233-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77233-124">См. также</span><span class="sxs-lookup"><span data-stu-id="77233-124">See also</span></span>

- [<span data-ttu-id="77233-125">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="77233-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="77233-126">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="77233-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="77233-127">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="77233-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
