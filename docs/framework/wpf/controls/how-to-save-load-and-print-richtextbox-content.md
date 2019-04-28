---
title: Практическое руководство. Сохранение, загрузка и печать содержимого RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
ms.openlocfilehash: 90581bee7815dafd44c3cae18a8af7394fee1e9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910602"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="3d3b3-102">Практическое руководство. Сохранение, загрузка и печать содержимого RichTextBox</span><span class="sxs-lookup"><span data-stu-id="3d3b3-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="3d3b3-103">В следующем примере показано, как сохранить содержимое <xref:System.Windows.Controls.RichTextBox> в файл, загрузить это содержимое обратно в <xref:System.Windows.Controls.RichTextBox>и напечатать содержимое.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d3b3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3d3b3-104">Example</span></span>  
 <span data-ttu-id="3d3b3-105">Ниже для примера приведена разметка.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="3d3b3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3d3b3-106">Example</span></span>  
 <span data-ttu-id="3d3b3-107">Ниже для примера приведен код.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3d3b3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3d3b3-108">See also</span></span>

- [<span data-ttu-id="3d3b3-109">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="3d3b3-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="3d3b3-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="3d3b3-110">TextBox Overview</span></span>](textbox-overview.md)
