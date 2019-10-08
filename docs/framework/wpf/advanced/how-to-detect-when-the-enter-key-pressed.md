---
title: Практическое руководство. Обнаружить нажатие клавиши ВВОД
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004820"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="3144b-102">Практическое руководство. Обнаружить нажатие клавиши ВВОД</span><span class="sxs-lookup"><span data-stu-id="3144b-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="3144b-103">В этом примере показано, как обнаружить нажатие клавиши <xref:System.Windows.Input.Key.Enter> на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="3144b-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="3144b-104">Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="3144b-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3144b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3144b-105">Example</span></span>  
 <span data-ttu-id="3144b-106">Когда пользователь нажимает клавишу <xref:System.Windows.Input.Key.Enter> в <xref:System.Windows.Controls.TextBox>, входные данные в текстовом поле появляется в другой области [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3144b-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="3144b-107">Следующий код XAML создает пользовательский интерфейс, состоящий из <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3144b-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="3144b-108">Следующий программный код создает обработчик событий <xref:System.Windows.UIElement.KeyDown>.</span><span class="sxs-lookup"><span data-stu-id="3144b-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="3144b-109">Если нажата клавиша <xref:System.Windows.Input.Key.Enter>, в <xref:System.Windows.Controls.TextBlock> отображается сообщение.</span><span class="sxs-lookup"><span data-stu-id="3144b-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="3144b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3144b-110">See also</span></span>

- [<span data-ttu-id="3144b-111">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="3144b-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="3144b-112">Общие сведения о перенаправленных событиях</span><span class="sxs-lookup"><span data-stu-id="3144b-112">Routed Events Overview</span></span>](routed-events-overview.md)
