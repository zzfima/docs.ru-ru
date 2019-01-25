---
title: Как выполнить Получение смещения визуального объекта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: ad45dee5b72594f30b141e3affbb26706af645aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645396"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="fd587-102">Как выполнить Получение смещения визуального объекта</span><span class="sxs-lookup"><span data-stu-id="fd587-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="fd587-103">Эти примеры демонстрируют получение значение смещения визуального объекта относительно своего родительского элемента, или любой предков или потомков.</span><span class="sxs-lookup"><span data-stu-id="fd587-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd587-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fd587-104">Example</span></span>  
 <span data-ttu-id="fd587-105">В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> , определенный с <xref:System.Windows.FrameworkElement.Margin%2A> значение 4.</span><span class="sxs-lookup"><span data-stu-id="fd587-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="fd587-106">В следующем примере кода показано, как использовать <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> метод для извлечения смещение <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fd587-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="fd587-107">Значения смещения содержатся в возвращаемом <xref:System.Windows.Vector> значение.</span><span class="sxs-lookup"><span data-stu-id="fd587-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="fd587-108">Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="fd587-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="fd587-109">В этом случае <xref:System.Windows.Vector.X%2A> равен 4, и <xref:System.Windows.Vector.Y%2A> — 4.</span><span class="sxs-lookup"><span data-stu-id="fd587-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="fd587-110">Возвращаемое значение смещения является относительно родительского элемента из <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="fd587-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="fd587-111">Если вы хотите вернуть значение смещения, не является относительно родительского элемента из <xref:System.Windows.Media.Visual>, используйте <xref:System.Windows.Media.Visual.TransformToAncestor%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="fd587-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="fd587-112">Получение смещения относительно предка</span><span class="sxs-lookup"><span data-stu-id="fd587-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="fd587-113">В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> , вложенный в двух <xref:System.Windows.Controls.StackPanel> объектов.</span><span class="sxs-lookup"><span data-stu-id="fd587-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="fd587-114">Ниже показаны результаты разметки.</span><span class="sxs-lookup"><span data-stu-id="fd587-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="fd587-115">![Значения смещения объектов](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="fd587-115">![Offset values of objects](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="fd587-116">TextBlock, вложенные в двух элементы управления StackPanel</span><span class="sxs-lookup"><span data-stu-id="fd587-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="fd587-117">В следующем примере кода показано, как использовать <xref:System.Windows.Media.Visual.TransformToAncestor%2A> метод для извлечения смещение <xref:System.Windows.Controls.TextBlock> относительно содержащего <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="fd587-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="fd587-118">Значения смещения содержатся в возвращаемом <xref:System.Windows.Media.GeneralTransform> значение.</span><span class="sxs-lookup"><span data-stu-id="fd587-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="fd587-119">Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значения для всех объектов класса <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="fd587-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="fd587-120">В этом случае <xref:System.Windows.Vector.X%2A> равно 28 (16 + 8 + 4), и <xref:System.Windows.Vector.Y%2A> равно 28.</span><span class="sxs-lookup"><span data-stu-id="fd587-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="fd587-121">Возвращаемое значение смещения задается относительно предком <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="fd587-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="fd587-122">Если вы хотите вернуть значение смещения относительно потомка <xref:System.Windows.Media.Visual>, используйте <xref:System.Windows.Media.Visual.TransformToDescendant%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="fd587-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="fd587-123">Получение смещения относительно потомка</span><span class="sxs-lookup"><span data-stu-id="fd587-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="fd587-124">В следующем примере разметки показан <xref:System.Windows.Controls.TextBlock> содержится в <xref:System.Windows.Controls.StackPanel> объекта.</span><span class="sxs-lookup"><span data-stu-id="fd587-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="fd587-125">В следующем примере кода показано, как использовать <xref:System.Windows.Media.Visual.TransformToDescendant%2A> метод для извлечения смещение <xref:System.Windows.Controls.StackPanel> относительно его дочерних <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="fd587-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="fd587-126">Значения смещения содержатся в возвращаемом <xref:System.Windows.Media.GeneralTransform> значение.</span><span class="sxs-lookup"><span data-stu-id="fd587-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="fd587-127">Смещение учитывает <xref:System.Windows.FrameworkElement.Margin%2A> значения для всех объектов.</span><span class="sxs-lookup"><span data-stu-id="fd587-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="fd587-128">В этом случае <xref:System.Windows.Vector.X%2A> равно -4, и <xref:System.Windows.Vector.Y%2A> равно -4.</span><span class="sxs-lookup"><span data-stu-id="fd587-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="fd587-129">Значения смещения являются отрицательными, поскольку родительский объект имеет отрицательное значение смещения по отношению к его дочернего объекта.</span><span class="sxs-lookup"><span data-stu-id="fd587-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd587-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fd587-130">See also</span></span>
- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="fd587-131">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="fd587-131">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
