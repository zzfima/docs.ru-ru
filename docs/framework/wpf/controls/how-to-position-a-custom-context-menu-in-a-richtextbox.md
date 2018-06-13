---
title: Практическое руководство. Использование пользовательского контекстного меню в RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: bde28cdb87bdaef3198d1efd3059fed3d0ae0ce2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553862"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="bea9a-102">Практическое руководство. Использование пользовательского контекстного меню в RichTextBox</span><span class="sxs-lookup"><span data-stu-id="bea9a-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="bea9a-103">В этом примере показано, как разместить пользовательское контекстное меню для <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="bea9a-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="bea9a-104">При реализации пользовательского контекстного меню для **RichTextBox** вы несете ответственность за обработку размещения контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="bea9a-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="bea9a-105">По умолчанию пользовательское контекстное меню открывается в центре **RichTextBox**.</span><span class="sxs-lookup"><span data-stu-id="bea9a-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bea9a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="bea9a-106">Example</span></span>  
 <span data-ttu-id="bea9a-107">Чтобы переопределить поведение расположения по умолчанию, добавьте прослушиватель для <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> события.</span><span class="sxs-lookup"><span data-stu-id="bea9a-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="bea9a-108">В приведенном ниже примере показано, как это сделать программным способом.</span><span class="sxs-lookup"><span data-stu-id="bea9a-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="bea9a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bea9a-109">Example</span></span>  
 <span data-ttu-id="bea9a-110">В следующем примере показана реализация соответствующего <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> прослушиватель событий.</span><span class="sxs-lookup"><span data-stu-id="bea9a-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="bea9a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bea9a-111">See Also</span></span>  
 [<span data-ttu-id="bea9a-112">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="bea9a-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="bea9a-113">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="bea9a-113">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
