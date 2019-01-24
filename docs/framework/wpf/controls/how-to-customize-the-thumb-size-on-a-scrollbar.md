---
title: Как выполнить Настройка размера ползунка в ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 2c77eb23c1a42051a7c2d81f3454eb51425fa034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590868"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="f9206-102">Как выполнить Настройка размера ползунка в ScrollBar</span><span class="sxs-lookup"><span data-stu-id="f9206-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="f9206-103">В этом разделе описывается настройка <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar> фиксированный размер и как задать минимальный размер <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="f9206-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9206-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f9206-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="f9206-105">Описание</span><span class="sxs-lookup"><span data-stu-id="f9206-105">Description</span></span>  
 <span data-ttu-id="f9206-106">В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с фиксированным размером.</span><span class="sxs-lookup"><span data-stu-id="f9206-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="f9206-107">В примере задается <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> свойство <xref:System.Windows.Controls.Primitives.Thumb> для <xref:System.Double.NaN> и задает высоту <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f9206-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="f9206-108">Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> , которые имеют фиксированную ширину, задайте ширину <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f9206-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="f9206-109">Код</span><span class="sxs-lookup"><span data-stu-id="f9206-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="f9206-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f9206-110">Description</span></span>  
 <span data-ttu-id="f9206-111">В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с минимальным размером.</span><span class="sxs-lookup"><span data-stu-id="f9206-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="f9206-112">В примере задается значение <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9206-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="f9206-113">Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> Минимальная ширина, задайте <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9206-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="f9206-114">Код</span><span class="sxs-lookup"><span data-stu-id="f9206-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f9206-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f9206-115">See also</span></span>
- [<span data-ttu-id="f9206-116">Стили и шаблоны элемента ScrollBar</span><span class="sxs-lookup"><span data-stu-id="f9206-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
