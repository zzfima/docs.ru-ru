---
title: "Практическое руководство. Закраска области с помощью системной кисти"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="19f8f-102">Практическое руководство. Закраска области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="19f8f-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="19f8f-103"><xref:System.Windows.SystemColors> Класс предоставляет доступ к системные кисти и цвета, такие как <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, и <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="19f8f-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="19f8f-104">Системная кисть является <xref:System.Windows.Media.SolidColorBrush> объект, который закрашивает область с помощью указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="19f8f-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="19f8f-105">Системная кисть всегда дает сплошную заливку; ее нельзя использовать для создания градиентной заливки.</span><span class="sxs-lookup"><span data-stu-id="19f8f-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="19f8f-106">Системные кисти можно использовать как статический или динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="19f8f-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="19f8f-107">Используйте динамический ресурс, если нужно автоматическое обновление кисти при изменении пользователем кисти во время выполнения приложения; в противном случае используйте статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="19f8f-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="19f8f-108">Класс SystemColors содержит разнообразные статические свойства, которые следуют строгому правилу именования:</span><span class="sxs-lookup"><span data-stu-id="19f8f-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="19f8f-109">*\<SystemColor>*Brush</span><span class="sxs-lookup"><span data-stu-id="19f8f-109">*\<SystemColor>*Brush</span></span>  
  
     <span data-ttu-id="19f8f-110">Возвращает статическую ссылку на <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="19f8f-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="19f8f-111">*\<SystemColor>*BrushKey</span><span class="sxs-lookup"><span data-stu-id="19f8f-111">*\<SystemColor>*BrushKey</span></span>  
  
     <span data-ttu-id="19f8f-112">Получает динамическую ссылку на <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="19f8f-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="19f8f-113">*\<SystemColor>*Color</span><span class="sxs-lookup"><span data-stu-id="19f8f-113">*\<SystemColor>*Color</span></span>  
  
     <span data-ttu-id="19f8f-114">Возвращает статическую ссылку на <xref:System.Windows.Media.Color> структуру указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="19f8f-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="19f8f-115">*\<SystemColor>*ColorKey</span><span class="sxs-lookup"><span data-stu-id="19f8f-115">*\<SystemColor>*ColorKey</span></span>  
  
     <span data-ttu-id="19f8f-116">Получает динамическую ссылку на <xref:System.Windows.Media.Color> структуру указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="19f8f-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="19f8f-117">Является системный цвет <xref:System.Windows.Media.Color> структуры, который может использоваться для настройки кисти.</span><span class="sxs-lookup"><span data-stu-id="19f8f-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="19f8f-118">Например, можно создать градиент с помощью системных цветов, задав <xref:System.Windows.Media.GradientStop.Color%2A> свойства <xref:System.Windows.Media.LinearGradientBrush> градиента объекта с системными цветами.</span><span class="sxs-lookup"><span data-stu-id="19f8f-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="19f8f-119">Пример см. в разделе [использование системных цветов в градиенте](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="19f8f-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f8f-120">Пример</span><span class="sxs-lookup"><span data-stu-id="19f8f-120">Example</span></span>  
 <span data-ttu-id="19f8f-121">В следующем примере используется динамическая ссылка на системную кисть для установки фона кнопки.</span><span class="sxs-lookup"><span data-stu-id="19f8f-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="19f8f-122">В следующем примере используется статическая ссылка на системную кисть для установки фона кнопки.</span><span class="sxs-lookup"><span data-stu-id="19f8f-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="19f8f-123">Пример, показывающий, как использовать системный цвет в градиенте см. в разделе [использование системных цветов в градиенте](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="19f8f-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f8f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="19f8f-124">See Also</span></span>  
 [<span data-ttu-id="19f8f-125">Использование системных цветов в градиенте</span><span class="sxs-lookup"><span data-stu-id="19f8f-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="19f8f-126">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="19f8f-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
