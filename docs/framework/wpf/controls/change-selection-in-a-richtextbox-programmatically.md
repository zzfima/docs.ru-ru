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
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001719"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="8e632-102">Изменение выделения в RichTextBox программными средствами</span><span class="sxs-lookup"><span data-stu-id="8e632-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="8e632-103">В этом примере показано, как программно изменить текущее выделение в <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="8e632-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="8e632-104">Этот параметр аналогичен так, как если бы пользователь выделил содержимое с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8e632-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e632-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8e632-105">Example</span></span>  
 <span data-ttu-id="8e632-106">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] коде описывается элемент <xref:System.Windows.Controls.RichTextBox> элемента управления с простым содержимым.</span><span class="sxs-lookup"><span data-stu-id="8e632-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="8e632-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8e632-107">Example</span></span>  
 <span data-ttu-id="8e632-108">В следующем коде программно выбирается произвольный текст, когда пользователь щелкает внутри <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="8e632-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8e632-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8e632-109">See also</span></span>

- [<span data-ttu-id="8e632-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8e632-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="8e632-111">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="8e632-111">TextBox Overview</span></span>](textbox-overview.md)
