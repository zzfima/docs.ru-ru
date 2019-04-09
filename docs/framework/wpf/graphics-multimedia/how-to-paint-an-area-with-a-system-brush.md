---
title: Практическое руководство. Заливка области с помощью системной кисти
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: e713903e2cfbb63cb64ceb94621317f9e76dea70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195050"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="5a067-102">Практическое руководство. Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="5a067-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="5a067-103"><xref:System.Windows.SystemColors> Класс предоставляет доступ к системным кистям и цветам, такие как <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, и <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a067-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="5a067-104">Системная кисть — это <xref:System.Windows.Media.SolidColorBrush> объект, который закрашивает область с помощью указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="5a067-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="5a067-105">Системная кисть всегда дает сплошную заливку; ее нельзя использовать для создания градиентной заливки.</span><span class="sxs-lookup"><span data-stu-id="5a067-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="5a067-106">Системные кисти можно использовать как статический или динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="5a067-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="5a067-107">Используйте динамический ресурс, если нужно автоматическое обновление кисти при изменении пользователем кисти во время выполнения приложения; в противном случае используйте статический ресурс.</span><span class="sxs-lookup"><span data-stu-id="5a067-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="5a067-108">Класс SystemColors содержит разнообразные статические свойства, которые следуют строгому правилу именования:</span><span class="sxs-lookup"><span data-stu-id="5a067-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="5a067-109">*\<SystemColor>* Brush</span><span class="sxs-lookup"><span data-stu-id="5a067-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="5a067-110">Возвращает статическую ссылку на <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="5a067-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="5a067-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="5a067-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="5a067-112">Возвращает динамическую ссылку <xref:System.Windows.Media.SolidColorBrush> указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="5a067-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="5a067-113">*\<SystemColor>* Color</span><span class="sxs-lookup"><span data-stu-id="5a067-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="5a067-114">Возвращает статическую ссылку на <xref:System.Windows.Media.Color> структуру указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="5a067-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="5a067-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="5a067-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="5a067-116">Возвращает динамическую ссылку <xref:System.Windows.Media.Color> структуру указанного системного цвета.</span><span class="sxs-lookup"><span data-stu-id="5a067-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="5a067-117">Системный цвет является <xref:System.Windows.Media.Color> структуры, который может использоваться для настройки кисти.</span><span class="sxs-lookup"><span data-stu-id="5a067-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="5a067-118">Например, можно создать с помощью системных цветов, задав градиент <xref:System.Windows.Media.GradientStop.Color%2A> свойства <xref:System.Windows.Media.LinearGradientBrush> градиента объекта с системными цветами.</span><span class="sxs-lookup"><span data-stu-id="5a067-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="5a067-119">Например, см. в разделе [использование системных цветов в градиенте](how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="5a067-119">For an example, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a067-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-120">Example</span></span>  
 <span data-ttu-id="5a067-121">В следующем примере используется динамическая ссылка на системную кисть для установки фона кнопки.</span><span class="sxs-lookup"><span data-stu-id="5a067-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="5a067-122">В следующем примере используется статическая ссылка на системную кисть для установки фона кнопки.</span><span class="sxs-lookup"><span data-stu-id="5a067-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="5a067-123">Пример, демонстрирующий использование системных цветов в градиенте, см. в разделе [использование системных цветов в градиенте](how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="5a067-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a067-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5a067-124">See also</span></span>

- [<span data-ttu-id="5a067-125">Использование системных цветов в градиенте</span><span class="sxs-lookup"><span data-stu-id="5a067-125">Use System Colors in a Gradient</span></span>](how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="5a067-126">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="5a067-126">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
