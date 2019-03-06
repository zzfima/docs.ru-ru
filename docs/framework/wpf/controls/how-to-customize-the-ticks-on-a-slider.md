---
title: Практическое руководство. Настройка делений на ползунке
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 438bd8aca4b44bc449415dc2b9a0ff2036d14eb5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368159"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="76aae-102">Практическое руководство. Настройка делений на ползунке</span><span class="sxs-lookup"><span data-stu-id="76aae-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="76aae-103">В этом примере показано, как создать <xref:System.Windows.Controls.Slider> элемента управления, содержащий деления.</span><span class="sxs-lookup"><span data-stu-id="76aae-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76aae-104">Пример</span><span class="sxs-lookup"><span data-stu-id="76aae-104">Example</span></span>  
 <span data-ttu-id="76aae-105"><xref:System.Windows.Controls.Primitives.TickBar> Отображается в случае <xref:System.Windows.Controls.Slider.TickPlacement%2A> присваивается значение, отличное от <xref:System.Windows.Controls.Primitives.TickPlacement.None>, который является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76aae-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="76aae-106">В следующем примере показано, как создать <xref:System.Windows.Controls.Slider> с <xref:System.Windows.Controls.Primitives.TickBar> отображает метки деления.</span><span class="sxs-lookup"><span data-stu-id="76aae-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="76aae-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A> И <xref:System.Windows.Controls.Slider.TickFrequency%2A> определяют расположение меток делений и интервал между ними.</span><span class="sxs-lookup"><span data-stu-id="76aae-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="76aae-108">При перемещении <xref:System.Windows.Controls.Primitives.Thumb>, всплывающие подсказки отображают значение <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="76aae-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="76aae-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Свойство определяет, где появляется подсказка.</span><span class="sxs-lookup"><span data-stu-id="76aae-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="76aae-110"><xref:System.Windows.Controls.Primitives.Thumb> Перемещений соответствуют расположению меток делений поскольку <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> присваивается `true`.</span><span class="sxs-lookup"><span data-stu-id="76aae-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="76aae-111">В следующем примере показано, как использовать <xref:System.Windows.Controls.Slider.Ticks%2A> свойства для создания метки вдоль делений <xref:System.Windows.Controls.Slider> через нерегулярные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="76aae-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="76aae-112">См. также</span><span class="sxs-lookup"><span data-stu-id="76aae-112">See also</span></span>
- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="76aae-113">[Практическое руководство. Привязка ползунка к значению свойства](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="76aae-113">[How to: Bind a Slider to a Property Value](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
