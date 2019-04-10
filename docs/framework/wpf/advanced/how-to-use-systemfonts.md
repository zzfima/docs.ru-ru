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
ms.openlocfilehash: 5976bc0cb8b34e68d5e89dd70a608d7e52ded332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216786"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="119c0-102">Практическое руководство. Использование SystemFonts</span><span class="sxs-lookup"><span data-stu-id="119c0-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="119c0-103">В этом примере показано, как использовать статические ресурсы <xref:System.Windows.SystemFonts> класс для изменения стиля или настроек кнопки.</span><span class="sxs-lookup"><span data-stu-id="119c0-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="119c0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="119c0-104">Example</span></span>  
 <span data-ttu-id="119c0-105">Системные ресурсы предоставляют несколько значений, определяемых системой, в качестве ресурсов и свойств, помогающих создавать визуальные элементы, согласованные с параметрами системы.</span><span class="sxs-lookup"><span data-stu-id="119c0-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <xref:System.Windows.SystemFonts> <span data-ttu-id="119c0-106">— Это класс, содержащий значения системного шрифта в виде статических свойств и свойства со ссылками на ключи ресурсов, которые могут использоваться для доступа к этим значениям динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="119c0-106">is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="119c0-107">Например <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> — <xref:System.Windows.SystemFonts> значение, и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> является ключом соответствующего ресурса.</span><span class="sxs-lookup"><span data-stu-id="119c0-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="119c0-108">В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать члены <xref:System.Windows.SystemFonts> как статические свойства или ссылки на динамические ресурсы (со статическим значением свойства в качестве ключа).</span><span class="sxs-lookup"><span data-stu-id="119c0-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="119c0-109">Используйте ссылку на динамический ресурс, если метрика шрифта должна автоматически обновляться во время выполнения приложения. В противном случае используйте ссылку на статическое значение.</span><span class="sxs-lookup"><span data-stu-id="119c0-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="119c0-110">К именам свойств, используемых в качестве ключей ресурсов, добавляется суффикс Key.</span><span class="sxs-lookup"><span data-stu-id="119c0-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="119c0-111">Приведенный ниже показано, как получить доступ и использовать свойства <xref:System.Windows.SystemFonts> как статических значений для изменения стиля или настроек кнопки.</span><span class="sxs-lookup"><span data-stu-id="119c0-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="119c0-112">Этот пример разметки присваивает <xref:System.Windows.SystemFonts> значения к кнопке.</span><span class="sxs-lookup"><span data-stu-id="119c0-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="119c0-113">Чтобы использовать значения из <xref:System.Windows.SystemFonts> в коде, не нужно использовать статическое значение или ссылку на динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="119c0-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="119c0-114">Вместо этого использовать неключевые свойства <xref:System.Windows.SystemFonts> класса.</span><span class="sxs-lookup"><span data-stu-id="119c0-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="119c0-115">Хотя неключевые свойства очевидно определены как статические, поведение времени выполнения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , размещенного по системе будут пересчитываться свойства в режиме реального времени и правильно учитываться вносимые пользователем изменения значений системы.</span><span class="sxs-lookup"><span data-stu-id="119c0-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="119c0-116">В приведенном ниже примере показано, как задать параметры шрифта кнопки.</span><span class="sxs-lookup"><span data-stu-id="119c0-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="119c0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="119c0-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="119c0-118">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="119c0-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="119c0-119">Использование SystemParameters</span><span class="sxs-lookup"><span data-stu-id="119c0-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="119c0-120">Использование разделов системных шрифтов</span><span class="sxs-lookup"><span data-stu-id="119c0-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="119c0-121">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="119c0-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="119c0-122">Расширение разметки x:Static</span><span class="sxs-lookup"><span data-stu-id="119c0-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="119c0-123">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="119c0-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="119c0-124">Расширение разметки DynamicResource</span><span class="sxs-lookup"><span data-stu-id="119c0-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
