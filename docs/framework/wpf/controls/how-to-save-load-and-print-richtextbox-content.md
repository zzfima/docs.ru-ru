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
ms.openlocfilehash: bcb368ababaac15dd92b11e43c22dfb705a7c0b3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365741"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="84abf-102">Практическое руководство. Сохранение, загрузка и печать содержимого RichTextBox</span><span class="sxs-lookup"><span data-stu-id="84abf-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="84abf-103">В следующем примере показано, как сохранить содержимое <xref:System.Windows.Controls.RichTextBox> в файл, загрузить это содержимое обратно в <xref:System.Windows.Controls.RichTextBox>и напечатать содержимое.</span><span class="sxs-lookup"><span data-stu-id="84abf-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84abf-104">Пример</span><span class="sxs-lookup"><span data-stu-id="84abf-104">Example</span></span>  
 <span data-ttu-id="84abf-105">Ниже для примера приведена разметка.</span><span class="sxs-lookup"><span data-stu-id="84abf-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="84abf-106">Пример</span><span class="sxs-lookup"><span data-stu-id="84abf-106">Example</span></span>  
 <span data-ttu-id="84abf-107">Ниже для примера приведен код.</span><span class="sxs-lookup"><span data-stu-id="84abf-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="84abf-108">См. также</span><span class="sxs-lookup"><span data-stu-id="84abf-108">See also</span></span>
- [<span data-ttu-id="84abf-109">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="84abf-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="84abf-110">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="84abf-110">TextBox Overview</span></span>](textbox-overview.md)
