---
title: "Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e05163bcbafd360e0929fe784ff1111bd0663ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="f150d-102">Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления</span><span class="sxs-lookup"><span data-stu-id="f150d-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="f150d-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester> Определяет, пересекается ли текущий росчерк stroke в другой.</span><span class="sxs-lookup"><span data-stu-id="f150d-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="f150d-104">Это полезно для создания элемента управления, который позволяет пользователю стирать части штриха, способ пользователь может выполнять на <xref:System.Windows.Controls.InkCanvas> при <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> равно <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="f150d-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f150d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f150d-105">Example</span></span>  
 <span data-ttu-id="f150d-106">В следующем примере создается пользовательский элемент управления, который позволяет пользователю стирать части росчерков.</span><span class="sxs-lookup"><span data-stu-id="f150d-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="f150d-107">В этом примере создается элемент управления, содержащий рукописного ввода при ее инициализации.</span><span class="sxs-lookup"><span data-stu-id="f150d-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="f150d-108">Создание элемента управления, который собирает рукописного ввода — [создания элемента управления ввода рукописного ввода](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="f150d-108">To create a control that collects ink, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
