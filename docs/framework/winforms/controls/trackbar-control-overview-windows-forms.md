---
title: "Общие сведения об элементе управления TrackBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccea982c45ab22a4b2ab81bc80c16dd472144bbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="43fb3-102">Общие сведения об элементе управления TrackBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="43fb3-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="43fb3-103">Windows Forms <xref:System.Windows.Forms.TrackBar> управления (иногда называют также элемент управления «ползунок») используется для просмотра данные большого объема или для визуальной настройки числовых параметров.</span><span class="sxs-lookup"><span data-stu-id="43fb3-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="43fb3-104"><xref:System.Windows.Forms.TrackBar> Управления состоит из двух частей: ползунка и делений.</span><span class="sxs-lookup"><span data-stu-id="43fb3-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="43fb3-105">Бегунка входит в состав, которое может быть настроено.</span><span class="sxs-lookup"><span data-stu-id="43fb3-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="43fb3-106">Его положение соответствует <xref:System.Windows.Forms.TrackBar.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="43fb3-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="43fb3-107">Деления — это визуальные индикаторы, расположенные через равные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="43fb3-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="43fb3-108">Ползунок перемещается с шагом, которые могут быть выровнены по горизонтали или вертикали.</span><span class="sxs-lookup"><span data-stu-id="43fb3-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="43fb3-109">Например можно использовать для управления мерцания курсора скорость или мыши скорости для системы полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="43fb3-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="43fb3-110">Основные свойства</span><span class="sxs-lookup"><span data-stu-id="43fb3-110">Key Properties</span></span>  
 <span data-ttu-id="43fb3-111">Ключевые свойства <xref:System.Windows.Forms.TrackBar> управления <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, и <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span><span class="sxs-lookup"><span data-stu-id="43fb3-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="43fb3-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>является меткой импульсов.</span><span class="sxs-lookup"><span data-stu-id="43fb3-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="43fb3-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>и <xref:System.Windows.Forms.TrackBar.Maximum%2A> являются наименьшим и наибольшим значениями, которые могут быть представлены на полосе ползунка.</span><span class="sxs-lookup"><span data-stu-id="43fb3-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="43fb3-114">Два важных свойства: <xref:System.Windows.Forms.TrackBar.SmallChange%2A> и <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span><span class="sxs-lookup"><span data-stu-id="43fb3-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="43fb3-115">Значение <xref:System.Windows.Forms.TrackBar.SmallChange%2A> свойство — количество позиций, перемещается в ответ на нажатии клавиши влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="43fb3-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="43fb3-116">Значение <xref:System.Windows.Forms.TrackBar.LargeChange%2A> свойство — количество позиций бегунка переходит в ответ на нажатии клавиши PAGE UP или PAGE DOWN или в ответ на мыши, нажимает на полосе слева от бегунка.</span><span class="sxs-lookup"><span data-stu-id="43fb3-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fb3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="43fb3-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="43fb3-118">Элемент управления TrackBar</span><span class="sxs-lookup"><span data-stu-id="43fb3-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
