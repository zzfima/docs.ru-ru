---
title: Практическое руководство. Использование SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 305d0cf18db5dc96b2d3cde863cf4ba2ae8dbb96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="abb76-102">Практическое руководство. Использование SystemFonts</span><span class="sxs-lookup"><span data-stu-id="abb76-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="abb76-103">В этом примере показано, как использовать статические ресурсы <xref:System.Windows.SystemFonts> класс для изменения стиля или настроек кнопки.</span><span class="sxs-lookup"><span data-stu-id="abb76-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abb76-104">Пример</span><span class="sxs-lookup"><span data-stu-id="abb76-104">Example</span></span>  
 <span data-ttu-id="abb76-105">Системные ресурсы предоставляют несколько значений, определяемых системой, в качестве ресурсов и свойств, помогающих создавать визуальные элементы, согласованные с параметрами системы.</span><span class="sxs-lookup"><span data-stu-id="abb76-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="abb76-106"><xref:System.Windows.SystemFonts> — Это класс, содержащий значения системного шрифта в виде статических свойств и свойств, которые ссылаются на ключи ресурсов, которые могут использоваться для доступа к этим значениями динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="abb76-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="abb76-107">Например <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> — <xref:System.Windows.SystemFonts> значение, и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> является ключом соответствующего ресурса.</span><span class="sxs-lookup"><span data-stu-id="abb76-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="abb76-108">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать члены <xref:System.Windows.SystemFonts> как статические свойства или ссылки динамического ресурса (со статическим значением свойства в качестве ключа).</span><span class="sxs-lookup"><span data-stu-id="abb76-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="abb76-109">Используйте ссылку на динамический ресурс, если метрика шрифта должна автоматически обновляться во время выполнения приложения. В противном случае используйте ссылку на статическое значение.</span><span class="sxs-lookup"><span data-stu-id="abb76-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abb76-110">К именам свойств, используемых в качестве ключей ресурсов, добавляется суффикс Key.</span><span class="sxs-lookup"><span data-stu-id="abb76-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="abb76-111">Приведенный ниже показано, как получить доступ и использование свойств объекта <xref:System.Windows.SystemFonts> как статических значений для изменения стиля или настроек кнопки.</span><span class="sxs-lookup"><span data-stu-id="abb76-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="abb76-112">Этот пример разметки присваивает <xref:System.Windows.SystemFonts> кнопке значения.</span><span class="sxs-lookup"><span data-stu-id="abb76-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="abb76-113">Чтобы использовать значения из <xref:System.Windows.SystemFonts> в коде, не нужно использовать статическое значение или ссылку на динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="abb76-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="abb76-114">Вместо этого используйте неключевые свойства <xref:System.Windows.SystemFonts> класса.</span><span class="sxs-lookup"><span data-stu-id="abb76-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="abb76-115">Хотя неключевые свойства очевидно определены как статические, поведение во время выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенного система будет пересчитывать свойства в режиме реального времени и правильно учитывать управляемые пользователем изменения значений системы.</span><span class="sxs-lookup"><span data-stu-id="abb76-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="abb76-116">В приведенном ниже примере показано, как задать параметры шрифта кнопки.</span><span class="sxs-lookup"><span data-stu-id="abb76-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="abb76-117">См. также</span><span class="sxs-lookup"><span data-stu-id="abb76-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="abb76-118">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="abb76-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="abb76-119">Использование SystemParameters</span><span class="sxs-lookup"><span data-stu-id="abb76-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="abb76-120">Использование разделов системных шрифтов</span><span class="sxs-lookup"><span data-stu-id="abb76-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="abb76-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="abb76-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="abb76-122">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="abb76-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="abb76-123">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="abb76-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="abb76-124">Расширение разметки DynamicResource</span><span class="sxs-lookup"><span data-stu-id="abb76-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
