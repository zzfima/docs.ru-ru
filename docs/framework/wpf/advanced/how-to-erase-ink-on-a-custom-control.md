---
title: Практическое руководство. Удаление данных рукописного ввода в пользовательском элементе управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365897"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="2cf0c-102">Практическое руководство. Удаление данных рукописного ввода в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="2cf0c-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="2cf0c-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester> Определяет, пересекается ли текущий росчерк одним росчерком.</span><span class="sxs-lookup"><span data-stu-id="2cf0c-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="2cf0c-104">Это полезно для создания элемента управления, который позволяет пользователю стирать части штриха, способ пользователь может на <xref:System.Windows.Controls.InkCanvas> при <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> присваивается <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="2cf0c-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cf0c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2cf0c-105">Example</span></span>  
 <span data-ttu-id="2cf0c-106">В следующем примере создается пользовательский элемент управления, позволяющий пользователю стирать части штрихов.</span><span class="sxs-lookup"><span data-stu-id="2cf0c-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="2cf0c-107">В этом примере создается элемент управления, содержащий рукописного ввода при инициализации.</span><span class="sxs-lookup"><span data-stu-id="2cf0c-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="2cf0c-108">Чтобы создать элемент управления, который собирает данные рукописного ввода, см. в разделе [Создание элемента управления рукописным ввода](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="2cf0c-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
