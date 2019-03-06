---
title: Практическое руководство. Настройка размера ползунка в ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 30fc72e3f0631b01777bf058c7a7470cc376a547
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354327"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="e2433-102">Практическое руководство. Настройка размера ползунка в ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e2433-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="e2433-103">В этом разделе описывается настройка <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar> фиксированный размер и как задать минимальный размер <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e2433-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2433-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e2433-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="e2433-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e2433-105">Description</span></span>  
 <span data-ttu-id="e2433-106">В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с фиксированным размером.</span><span class="sxs-lookup"><span data-stu-id="e2433-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="e2433-107">В примере задается <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> свойство <xref:System.Windows.Controls.Primitives.Thumb> для <xref:System.Double.NaN> и задает высоту <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="e2433-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="e2433-108">Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> , которые имеют фиксированную ширину, задайте ширину <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="e2433-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e2433-109">Код</span><span class="sxs-lookup"><span data-stu-id="e2433-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="e2433-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e2433-110">Description</span></span>  
 <span data-ttu-id="e2433-111">В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с минимальным размером.</span><span class="sxs-lookup"><span data-stu-id="e2433-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="e2433-112">В примере задается значение <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2433-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="e2433-113">Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> Минимальная ширина, задайте <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2433-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e2433-114">Код</span><span class="sxs-lookup"><span data-stu-id="e2433-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e2433-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e2433-115">See also</span></span>
- [<span data-ttu-id="e2433-116">Стили и шаблоны элемента ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e2433-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
