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
ms.openlocfilehash: ff82b0bfc1983240431e582dbd78778dc4469241
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459942"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="955cd-102">Расширение разметки x:NULL</span><span class="sxs-lookup"><span data-stu-id="955cd-102">x:Null Markup Extension</span></span>
<span data-ttu-id="955cd-103">Указывает `null` как значение для элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="955cd-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="955cd-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="955cd-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="955cd-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="955cd-105">Remarks</span></span>  
 <span data-ttu-id="955cd-106">Ключевое слово для пустой ссылки в C# параметре и C++ равно null.</span><span class="sxs-lookup"><span data-stu-id="955cd-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="955cd-107">Ключевое слово Microsoft Visual Basic для пустой ссылки имеет `Nothing`, но в качестве использования XAML всегда используется `{x:Null}`, независимо от того, какой язык кода программной части связан с XAML.</span><span class="sxs-lookup"><span data-stu-id="955cd-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="955cd-108">Расширение разметки `x:Null` не имеет устанавливаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="955cd-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="955cd-109">Использование значения NULL часто связано с выкрытием члена XAML <xref:System.Nullable%601> значение CLR.</span><span class="sxs-lookup"><span data-stu-id="955cd-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="955cd-110">Расширение разметки `x:Null`, как и все расширения разметки XAML, использует фигурные скобки (`{,}`) для экранирования обработки значений атрибутов, отличных от литералов или ссылок обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="955cd-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="955cd-111">Синтаксис атрибутов — это синтаксис, который чаще всего используется с этим расширением разметки.</span><span class="sxs-lookup"><span data-stu-id="955cd-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="955cd-112">Синтаксис объектного элемента `<x:Null />` технически возможно, но редко используется, поскольку у расширения разметки `x:Null` нет позиционированных параметров или аргументов создания.</span><span class="sxs-lookup"><span data-stu-id="955cd-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="955cd-113">Дополнительные сведения о расширениях разметки см. в разделе [расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="955cd-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="955cd-114">В .NET Framework службах XAML обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.NullExtension>.</span><span class="sxs-lookup"><span data-stu-id="955cd-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="955cd-115">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="955cd-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="955cd-116">Обратите внимание, что `null` не обязательно является начальным значением свойства зависимости ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="955cd-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="955cd-117">Начальное значение по умолчанию может различаться для каждого свойства зависимости и может быть основано на метаданных, относящихся к свойству.</span><span class="sxs-lookup"><span data-stu-id="955cd-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="955cd-118">Многие свойства зависимостей не принимают `null` в качестве значения с помощью разметки или кода из-за реализаций обратного вызова проверки.</span><span class="sxs-lookup"><span data-stu-id="955cd-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="955cd-119">Дополнительные сведения о свойствах зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="955cd-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955cd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="955cd-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="955cd-121">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="955cd-121">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="955cd-122">Расширения разметки и XAML WPF</span><span class="sxs-lookup"><span data-stu-id="955cd-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
