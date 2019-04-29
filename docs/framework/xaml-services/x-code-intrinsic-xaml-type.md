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
ms.openlocfilehash: 7bb78b05be7b3edc4471bc276010eabd92a07a14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971851"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="3b4cb-102">Встроенный тип XAML x:Code</span><span class="sxs-lookup"><span data-stu-id="3b4cb-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="3b4cb-103">Позволяет помещать код в рабочем XAML.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="3b4cb-104">Такой код может компилироваться либо с любой реализации обработчика XAML, которая компилирует XAML или влево в рабочей среде XAML для использования более поздней версии, например для интерпретации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="3b4cb-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="3b4cb-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="3b4cb-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b4cb-106">Remarks</span></span>  
 <span data-ttu-id="3b4cb-107">Код внутри `x:Code` элемент директивы XAML является по-прежнему интерпретируется в общее пространство имен XML и пространства имен XAML, предоставляемые.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="3b4cb-108">Таким образом, это обычно потребует вложить код, используемый для `x:Code` внутри `CDATA` сегмента.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="3b4cb-109">`x:Code` не допускается для всех возможных механизмов развертывания рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="3b4cb-110">Код должен быть скомпилирован в конкретных платформах (например, WPF).</span><span class="sxs-lookup"><span data-stu-id="3b4cb-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="3b4cb-111">В других платформах `x:Code` использования обычно может быть запрещено.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="3b4cb-112">Для платформ, которые разрешают управляемых `x:Code` содержимого правильного компилятора языка для `x:Code` содержимое определяется параметрами и целевыми объектами содержащего проекта, который используется для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="3b4cb-113">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="3b4cb-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="3b4cb-114">Код объявлены внутри `x:Code` для WPF, имеет несколько существенных ограничений:</span><span class="sxs-lookup"><span data-stu-id="3b4cb-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="3b4cb-115">`x:Code` Элемент директивы должен быть непосредственным дочерним элементом корневого элемента XAML производства.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="3b4cb-116">[Директива x: Class](x-class-directive.md) должен быть предоставлен в родительском корневом элементе.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="3b4cb-117">Код помещен в `x:Code` будет рассматриваться при компиляции в пределах разделяемый класс, который уже создан для этой страницы XAML.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="3b4cb-118">Поэтому весь код вами необходимо членам или переменным этого разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="3b4cb-119">Невозможно определить дополнительные классы, кроме вложенного класса внутри разделяемого класса (допускается вложенность, но он не является типичным, поскольку вложенные классы не могут ссылаться на XAML).</span><span class="sxs-lookup"><span data-stu-id="3b4cb-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="3b4cb-120">Пространства имен CLR, отличном от пространства имен, который используется для существующего разделяемого класса не определены или добавлен.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="3b4cb-121">Ссылки на сущности кода за пределами пространства имен CLR разделяемого класса должен иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="3b4cb-122">Члены объявленные переопределения, чтобы переопределяемые члены разделяемого класса, необходимо указать с помощью ключевого слова переопределения для конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="3b4cb-123">Если члены, объявленные в `x:Code` область конфликтуют с членами разделяемого класса, могут быть созданы из XAML, таким образом, что компилятор сообщает конфликт, файл XAML не удается скомпилировать или загрузить.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4cb-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3b4cb-124">See also</span></span>

- [<span data-ttu-id="3b4cb-125">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="3b4cb-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="3b4cb-126">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="3b4cb-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="3b4cb-127">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="3b4cb-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
