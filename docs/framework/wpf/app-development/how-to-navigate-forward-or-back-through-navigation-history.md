---
title: "Практическое руководство. Переход вперед или назад по журналу навигации"
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
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78fd9fec6a93c100da6b4e7174376a963ae8beb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="e6a6c-102">Практическое руководство. Переход вперед или назад по журналу навигации</span><span class="sxs-lookup"><span data-stu-id="e6a6c-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="e6a6c-103">В этом примере показано, как перейти вперед или назад для записи в журнале навигации.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a6c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e6a6c-104">Example</span></span>  
 <span data-ttu-id="e6a6c-105">Код, выполняемый из содержимого в следующие узлы можно перейти вперед или назад по истории навигации, одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="e6a6c-106"><xref:System.Windows.Navigation.NavigationWindow>с помощью<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e6a6c-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="e6a6c-107"><xref:System.Windows.Controls.Frame>с помощью<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e6a6c-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="e6a6c-108">Прежде чем можно будет перейти вперед на одну запись, необходимо сначала записать отсутствии записей в журнале прямой навигации путем проверки **CanGoForward** свойство.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="e6a6c-109">Чтобы перейти вперед на одну запись, вызовите **GoForward** метод.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="e6a6c-110">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e6a6c-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="e6a6c-111">Прежде чем можно переходить назад на одну запись, необходимо сначала записать отсутствии записей в журнале переходов назад путем проверки **CanGoBack** свойство.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="e6a6c-112">Чтобы перейти назад на одну запись, вызовите **GoBack** метод.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="e6a6c-113">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e6a6c-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="e6a6c-114">**CanGoForward**, **GoForward**, **CanGoBack**, и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6a6c-115">При вызове метода **GoForward**, и нет ни одной записи в журнал прямой навигации, или при вызове метода **GoBack**, и нет ни одной записи в журнале переходов назад <xref:System.InvalidOperationException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="e6a6c-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
