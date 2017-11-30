---
title: "Практическое руководство. Определение нажатия клавиши \"Enter\""
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
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8311083b4b82d4ab4827e8d0a2cf958c67347014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="61e09-102">Практическое руководство. Определение нажатия клавиши "Enter"</span><span class="sxs-lookup"><span data-stu-id="61e09-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="61e09-103">В этом примере показано, как определить, когда <xref:System.Windows.Input.Key.Enter> клавиши на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="61e09-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="61e09-104">В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл кода.</span><span class="sxs-lookup"><span data-stu-id="61e09-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61e09-105">Пример</span><span class="sxs-lookup"><span data-stu-id="61e09-105">Example</span></span>  
 <span data-ttu-id="61e09-106">Когда пользователь нажимает <xref:System.Windows.Input.Key.Enter> ключа в <xref:System.Windows.Controls.TextBox>, входные данные в текстовом поле отображается в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61e09-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="61e09-107">Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61e09-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="61e09-108">Следующий код создает <xref:System.Windows.UIElement.KeyDown> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="61e09-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="61e09-109">Если ключ, нажатая <xref:System.Windows.Input.Key.Enter> ключа, сообщение отображается в <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="61e09-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="61e09-110">См. также</span><span class="sxs-lookup"><span data-stu-id="61e09-110">See Also</span></span>  
 [<span data-ttu-id="61e09-111">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="61e09-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="61e09-112">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="61e09-112">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
