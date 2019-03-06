---
title: Практическое руководство. Обнаружить, когда нажата клавиша ВВОД
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1796127d33087a3fd4504d03f175f8afe5323630
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351870"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="eff42-102">Практическое руководство. Обнаружить, когда нажата клавиша ВВОД</span><span class="sxs-lookup"><span data-stu-id="eff42-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="eff42-103">В этом примере показано, как определить, когда <xref:System.Windows.Input.Key.Enter> клавиши на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="eff42-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="eff42-104">В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл с выделенным кодом.</span><span class="sxs-lookup"><span data-stu-id="eff42-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eff42-105">Пример</span><span class="sxs-lookup"><span data-stu-id="eff42-105">Example</span></span>  
 <span data-ttu-id="eff42-106">Когда пользователь нажимает <xref:System.Windows.Input.Key.Enter> в <xref:System.Windows.Controls.TextBox>, входные данные в текстовом поле отображается в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eff42-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="eff42-107">Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="eff42-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="eff42-108">Следующий код создает <xref:System.Windows.UIElement.KeyDown> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="eff42-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="eff42-109">Если нажата клавиша является <xref:System.Windows.Input.Key.Enter> ключа, выводится сообщение в <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="eff42-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="eff42-110">См. также</span><span class="sxs-lookup"><span data-stu-id="eff42-110">See also</span></span>
- [<span data-ttu-id="eff42-111">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="eff42-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="eff42-112">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="eff42-112">Routed Events Overview</span></span>](routed-events-overview.md)
