---
title: Изменение выделения в RichTextBox программными средствами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e8ad33956f1a9fdddc728457e6c302635115b709
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="c3d3a-102">Изменение выделения в RichTextBox программными средствами</span><span class="sxs-lookup"><span data-stu-id="c3d3a-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="c3d3a-103">В этом примере показано, как программно изменить текущее выделение в <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="c3d3a-104">Этот параметр является таким же, как если бы пользователь выделил содержимое с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d3a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c3d3a-105">Example</span></span>  
 <span data-ttu-id="c3d3a-106">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] код описывает именованного <xref:System.Windows.Controls.RichTextBox> управления с простым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c3d3a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c3d3a-107">Example</span></span>  
 <span data-ttu-id="c3d3a-108">В следующем коде программно выбирается произвольный текст при щелчке внутри <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="c3d3a-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c3d3a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c3d3a-109">See Also</span></span>  
 [<span data-ttu-id="c3d3a-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c3d3a-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="c3d3a-111">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="c3d3a-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
