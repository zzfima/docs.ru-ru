---
title: Расширение разметки x:NULL
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484711"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="98a1e-102">Расширение разметки x:NULL</span><span class="sxs-lookup"><span data-stu-id="98a1e-102">x:Null Markup Extension</span></span>
<span data-ttu-id="98a1e-103">Задает `null` в качестве значения для элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="98a1e-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="98a1e-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="98a1e-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="98a1e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="98a1e-105">Remarks</span></span>  
 <span data-ttu-id="98a1e-106">Ключевое слово для пустой ссылки в C# параметре и C++ равно null.</span><span class="sxs-lookup"><span data-stu-id="98a1e-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="98a1e-107">Ключевое слово Microsoft Visual Basic для пустой ссылки — `Nothing`это, но всегда используется `{x:Null}` как использование XAML, независимо от того, какой язык кода программной части связан с XAML.</span><span class="sxs-lookup"><span data-stu-id="98a1e-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="98a1e-108">Расширение `x:Null` разметки не имеет устанавливаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="98a1e-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="98a1e-109">Использование значения NULL часто связано с выдержкой из XAML-элемента в значении CLR <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="98a1e-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="98a1e-110">Расширение разметки, как и все расширения разметки XAML, использует фигурные`{,}`скобки () для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий. `x:Null`</span><span class="sxs-lookup"><span data-stu-id="98a1e-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="98a1e-111">Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="98a1e-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="98a1e-112">Синтаксис `<x:Null />` объектного элемента технически возможен, но редко используется, `x:Null` так как расширение разметки не имеет параметров позиционирования или аргументов конструкции.</span><span class="sxs-lookup"><span data-stu-id="98a1e-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="98a1e-113">Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="98a1e-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="98a1e-114">В .NET Framework службах XAML обработка этого расширения разметки определяется <xref:System.Windows.Markup.NullExtension> классом.</span><span class="sxs-lookup"><span data-stu-id="98a1e-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="98a1e-115">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="98a1e-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="98a1e-116">Обратите `null` внимание, что не обязательно является начальным значением свойства зависимости ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="98a1e-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="98a1e-117">Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству.</span><span class="sxs-lookup"><span data-stu-id="98a1e-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="98a1e-118">Многие свойства зависимостей не принимаются `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки.</span><span class="sxs-lookup"><span data-stu-id="98a1e-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="98a1e-119">Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98a1e-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98a1e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="98a1e-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="98a1e-121">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="98a1e-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="98a1e-122">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="98a1e-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
