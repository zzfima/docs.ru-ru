---
title: "Практическое руководство. Извлечение выделенного текста"
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d5e1c362c02d2d1d9e1840ea2a55df6875a80ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="944ed-102">Практическое руководство. Извлечение выделенного текста</span><span class="sxs-lookup"><span data-stu-id="944ed-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="944ed-103">В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.SelectedText%2A> свойства, чтобы получить текст, который пользователь выбрал в <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="944ed-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="944ed-104">Пример</span><span class="sxs-lookup"><span data-stu-id="944ed-104">Example</span></span>  
 <span data-ttu-id="944ed-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере показано определение <xref:System.Windows.Controls.TextBox> управления, который содержит некоторый текст, чтобы выбрать, и <xref:System.Windows.Controls.Button> управления с заданными <xref:System.Windows.Controls.Button.OnClick%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="944ed-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="944ed-106">В этом примере кнопка со связанным <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий используется для извлечения выбранного текста.</span><span class="sxs-lookup"><span data-stu-id="944ed-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="944ed-107">Когда пользователь нажимает кнопку, <xref:System.Windows.Controls.Button.OnClick%2A> метод копирует любой выделенный текст в текстовом поле в строку.</span><span class="sxs-lookup"><span data-stu-id="944ed-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="944ed-108">Обстоятельствах для, на которые выбранный текст является извлечения (нажатию кнопки), также действие, выполняемое с выделенным (копирование выделенного текста в строку), можно легко изменить для размещения разнообразных сценариях.</span><span class="sxs-lookup"><span data-stu-id="944ed-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="944ed-109">Пример</span><span class="sxs-lookup"><span data-stu-id="944ed-109">Example</span></span>  
 <span data-ttu-id="944ed-110">Следующие [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] примере <xref:System.Windows.Controls.Button.OnClick%2A> обработчик событий для кнопки, определенные в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для этого примера.</span><span class="sxs-lookup"><span data-stu-id="944ed-110">The following [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="944ed-111">См. также</span><span class="sxs-lookup"><span data-stu-id="944ed-111">See Also</span></span>  
 [<span data-ttu-id="944ed-112">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="944ed-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="944ed-113">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="944ed-113">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
