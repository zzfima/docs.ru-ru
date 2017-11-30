---
title: "Встроенный тип XAML x:Code"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d1b21e2a654b18547c8da7da724c87946724f71f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="bdb65-102">Встроенный тип XAML x:Code</span><span class="sxs-lookup"><span data-stu-id="bdb65-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="bdb65-103">Позволяет помещать код в пределах рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="bdb65-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="bdb65-104">Такой код может быть скомпилирован либо с любой реализацией процессора XAML, который компилирует код XAML, либо слева в создании XAML для использования в дальнейшем например интерпретацию средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="bdb65-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="bdb65-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="bdb65-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="bdb65-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdb65-106">Remarks</span></span>  
 <span data-ttu-id="bdb65-107">Код в `x:Code` — элемент директивы XAML, по-прежнему интерпретируется в общее пространство имен XML и пространства имен XAML, предоставляемые.</span><span class="sxs-lookup"><span data-stu-id="bdb65-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="bdb65-108">Таким образом, обычно необходимо заключить код, используемый для `x:Code` внутри `CDATA` сегмента.</span><span class="sxs-lookup"><span data-stu-id="bdb65-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="bdb65-109">`x:Code`для всех возможных механизмов развертывания из рабочей среды XAML не разрешено.</span><span class="sxs-lookup"><span data-stu-id="bdb65-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="bdb65-110">Код должен быть скомпилирован в конкретных платформах (например, WPF).</span><span class="sxs-lookup"><span data-stu-id="bdb65-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="bdb65-111">В других платформах `x:Code` использования обычно может быть запрещено.</span><span class="sxs-lookup"><span data-stu-id="bdb65-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="bdb65-112">Для платформ, разрешающих использование управляемого `x:Code` содержимого правильный компилятор языка для `x:Code` содержимого определяется параметрами и целевыми объектами содержащего проекта, который используется для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="bdb65-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="bdb65-113">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="bdb65-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="bdb65-114">Код объявленная внутри `x:Code` для WPF имеет несколько существенных ограничений:</span><span class="sxs-lookup"><span data-stu-id="bdb65-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="bdb65-115">`x:Code` Элемент директивы должен быть непосредственным дочерним элементом корневого элемента рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="bdb65-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="bdb65-116">[Директива x: Class](../../../docs/framework/xaml-services/x-class-directive.md) должен быть предоставлен в родительском корневом элементе.</span><span class="sxs-lookup"><span data-stu-id="bdb65-116">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="bdb65-117">Код помещен в `x:Code` будет рассматриваться при компиляции в пределах разделяемого класса, который уже создан для этой страницы XAML.</span><span class="sxs-lookup"><span data-stu-id="bdb65-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="bdb65-118">Поэтому весь код, который определяется необходимо членам или переменным этого разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="bdb65-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="bdb65-119">Невозможно определить дополнительные классы, кроме вложенного класса внутри разделяемого класса (допускается вложенность, но он не является типичным, поскольку вложенные классы не могут ссылаться на XAML).</span><span class="sxs-lookup"><span data-stu-id="bdb65-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="bdb65-120">Пространства имен CLR, отличные от имен, которое используется для существующего разделяемого класса не определены или добавлен.</span><span class="sxs-lookup"><span data-stu-id="bdb65-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="bdb65-121">Ссылки на сущности кода за пределами пространства имен CLR разделяемого класса должны иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="bdb65-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="bdb65-122">Если элементы объявляемого переопределениями переопределяемые члены разделяемого класса, необходимо указать с помощью ключевого слова переопределения для конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="bdb65-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="bdb65-123">Если члены, объявленные в `x:Code` области конфликтуют с членами разделяемого класса, созданного из XAML, таким образом, что компилятор сообщает конфликт, XAML-файл не удается скомпилировать или загрузить.</span><span class="sxs-lookup"><span data-stu-id="bdb65-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb65-124">См. также</span><span class="sxs-lookup"><span data-stu-id="bdb65-124">See Also</span></span>  
 [<span data-ttu-id="bdb65-125">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="bdb65-125">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="bdb65-126">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="bdb65-126">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="bdb65-127">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="bdb65-127">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
