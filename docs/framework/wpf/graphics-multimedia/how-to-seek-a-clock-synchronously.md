---
title: Практическое руководство. Установка часов в синхронном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356001"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="f869f-102">Практическое руководство. Установка часов в синхронном режиме</span><span class="sxs-lookup"><span data-stu-id="f869f-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="f869f-103">Используйте <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> метод для часов до определенной точки в синхронном.</span><span class="sxs-lookup"><span data-stu-id="f869f-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="f869f-104">В следующем примере показано, как <xref:System.Windows.Media.Animation.ClockController.Seek%2A> и <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> методы <xref:System.Windows.Media.Animation.ClockController>.</span><span class="sxs-lookup"><span data-stu-id="f869f-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="f869f-105">В этом примере показано, как выполнить поиск <xref:System.Windows.Media.Animation.Clock>; пример, демонстрирующий поиск раскадровки, см. в разделе [поиск раскадровки синхронно](how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="f869f-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="f869f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f869f-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
