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
ms.openlocfilehash: 34a2de71bec9b0929070aa908741de38b5904643
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58029364"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="7276c-102">Расширение разметки x:NULL</span><span class="sxs-lookup"><span data-stu-id="7276c-102">x:Null Markup Extension</span></span>
<span data-ttu-id="7276c-103">Указывает `null` как значение для элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="7276c-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7276c-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="7276c-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="7276c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7276c-105">Remarks</span></span>  
 <span data-ttu-id="7276c-106">Ключевое слово для ссылкой на null в C# и [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="7276c-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="7276c-107">Ключевое слово Microsoft Visual Basic, ссылку на null является `Nothing`, но всегда `{x:Null}` как XAML использование независимо от того, какой язык кода, нужно связать с XAML.</span><span class="sxs-lookup"><span data-stu-id="7276c-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="7276c-108">`x:Null` Расширение разметки получает отсутствуют задаваемые свойства.</span><span class="sxs-lookup"><span data-stu-id="7276c-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="7276c-109">Null использования часто связывается с возможностью доступа члена XAML среды CLR <xref:System.Nullable%601> значение.</span><span class="sxs-lookup"><span data-stu-id="7276c-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="7276c-110">`x:Null` Расширения разметки, как и все расширения разметки XAML, используются фигурные скобки (`{,}`) для экранирования обработки значений атрибута не литералы или ссылки на обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7276c-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="7276c-111">Синтаксис атрибута является синтаксис, наиболее часто используемый с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="7276c-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="7276c-112">Синтаксис элемента объекта `<x:Null />` технически возможно, но используется редко, так как `x:Null` расширения разметки не имеет позиционные параметры и аргументы построения.</span><span class="sxs-lookup"><span data-stu-id="7276c-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="7276c-113">Сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7276c-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="7276c-114">В службах XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.NullExtension> класса.</span><span class="sxs-lookup"><span data-stu-id="7276c-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="7276c-115">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="7276c-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="7276c-116">Обратите внимание, что `null` не обязательно начальное значение не задано для свойства зависимостей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="7276c-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="7276c-117">Начальное значение по умолчанию могут различаться для каждого свойства зависимости и могут быть основаны на метаданные, относящиеся к свойствам.</span><span class="sxs-lookup"><span data-stu-id="7276c-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="7276c-118">Многие свойства зависимостей не принимают `null` как значение, либо через разметки или кода из-за их реализации обратного вызова проверки.</span><span class="sxs-lookup"><span data-stu-id="7276c-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="7276c-119">Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7276c-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7276c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7276c-120">See also</span></span>
- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="7276c-121">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7276c-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="7276c-122">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="7276c-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
