---
title: Практическое руководство. Переход вперед или назад по журналу навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 00a41fcf85583ec0d081a2fa099f3a77cfcd2900
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625358"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="6b2a2-102">Практическое руководство. Переход вперед или назад по журналу навигации</span><span class="sxs-lookup"><span data-stu-id="6b2a2-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="6b2a2-103">В этом примере показано, как для перехода к записи в журнале переходов вперед или назад.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b2a2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6b2a2-104">Example</span></span>  
 <span data-ttu-id="6b2a2-105">Код, выполняемый из содержимого в следующими узлами можно перейти вперед или назад по журналу переходов, одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="6b2a2-106"><xref:System.Windows.Navigation.NavigationWindow> С помощью <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="6b2a2-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="6b2a2-107"><xref:System.Windows.Controls.Frame> С помощью <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="6b2a2-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="6b2a2-108">Прежде чем можно будет перейти вперед на одну запись, сначала следует проверить, записи в журнале переходов вперед, проверяя **CanGoForward** свойство.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="6b2a2-109">Чтобы перейти вперед на одну запись, необходимо вызвать **GoForward** метод.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="6b2a2-110">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6b2a2-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="6b2a2-111">Прежде чем вы можете перейти назад на одну запись, необходимо сначала проверить, записи в журнале переходов назад, проверяя **CanGoBack** свойство.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="6b2a2-112">Чтобы перейти назад на одну запись, необходимо вызвать **GoBack** метод.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="6b2a2-113">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6b2a2-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="6b2a2-114">**Значение свойства CanGoForward**, **GoForward**, **CanGoBack**, и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b2a2-115">При вызове метода **GoForward**, и нет записей в журнале переходов вперед, или при вызове **GoBack**, и нет записей в журнале переходов назад, <xref:System.InvalidOperationException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="6b2a2-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
