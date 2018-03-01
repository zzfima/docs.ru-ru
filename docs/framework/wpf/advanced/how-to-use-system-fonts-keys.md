---
title: "Как использовать разделы системных шрифтов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 53538c64d2af5d8407f79848ddcd01f7665303c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="0466e-102">Как использовать разделы системных шрифтов</span><span class="sxs-lookup"><span data-stu-id="0466e-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="0466e-103">Системные ресурсы предоставляют ряд метрик системы в качестве ресурсов, что помогает разработчикам создавать визуальные элементы, совместимые с параметрами системы.</span><span class="sxs-lookup"><span data-stu-id="0466e-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="0466e-104"><xref:System.Windows.SystemFonts>— Это класс, содержащий значения системных шрифтов и системных ресурсов шрифтов, которые привязаны к значениям — например, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> и <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="0466e-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="0466e-105">Метрики системных шрифтов могут использоваться в качестве статического или динамического ресурса.</span><span class="sxs-lookup"><span data-stu-id="0466e-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="0466e-106">Используйте динамический ресурс, если требуется метрика шрифта для автоматического обновления во время выполнения приложения. В противном случае используйте статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="0466e-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0466e-107">Динамические ресурсы имеют ключевое слово *ключ* добавляется к имени свойства.</span><span class="sxs-lookup"><span data-stu-id="0466e-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="0466e-108">В приведенном ниже примере показано, как получить доступ к ресурсам динамических системных шрифтов и использовать их для создания стиля или настройки кнопки.</span><span class="sxs-lookup"><span data-stu-id="0466e-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="0466e-109">Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] примере создается стиль кнопки, которая присваивает <xref:System.Windows.SystemFonts> кнопке значения.</span><span class="sxs-lookup"><span data-stu-id="0466e-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0466e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0466e-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="0466e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0466e-111">See Also</span></span>  
 [<span data-ttu-id="0466e-112">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="0466e-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="0466e-113">Использование SystemParameters</span><span class="sxs-lookup"><span data-stu-id="0466e-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="0466e-114">Использование SystemFonts</span><span class="sxs-lookup"><span data-stu-id="0466e-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
