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
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961348"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="92cf6-102">Практическое руководство. Переход вперед или назад по журналу навигации</span><span class="sxs-lookup"><span data-stu-id="92cf6-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="92cf6-103">В этом примере показано, как перейти вперед или назад к записям в журнале навигации.</span><span class="sxs-lookup"><span data-stu-id="92cf6-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92cf6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="92cf6-104">Example</span></span>  
 <span data-ttu-id="92cf6-105">Код, запускаемый из содержимого на следующих узлах, может перемещаться вперед или назад через журнал навигации, по одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="92cf6-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="92cf6-106"><xref:System.Windows.Navigation.NavigationWindow>использующ<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="92cf6-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="92cf6-107"><xref:System.Windows.Controls.Frame>использующ<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="92cf6-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="92cf6-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="92cf6-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="92cf6-109">Прежде чем можно будет перейти вперед к одной записи, необходимо сначала проверить наличие записей в журнале переходов вперед, проверив свойство **кангофорвард** .</span><span class="sxs-lookup"><span data-stu-id="92cf6-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="92cf6-110">Для перехода вперед на одну запись вызывается метод **GoForward** .</span><span class="sxs-lookup"><span data-stu-id="92cf6-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="92cf6-111">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="92cf6-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="92cf6-112">Прежде чем переходить к одной записи, необходимо сначала проверить наличие записей в журнале переходов назад, изучив свойство **CanGoBack** .</span><span class="sxs-lookup"><span data-stu-id="92cf6-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="92cf6-113">Для перехода назад к одной записи вызывается метод **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="92cf6-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="92cf6-114">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="92cf6-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="92cf6-115">**Кангофорвард**, **GoForward**, **CanGoBack**и **GoBack** реализуются с помощью <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="92cf6-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92cf6-116">При вызове **GoForward**и отсутствии записей в журнале переходов вперед или при вызове программы **GoBack**и отсутствии записей в <xref:System.InvalidOperationException> журнале переходов назад создается исключение.</span><span class="sxs-lookup"><span data-stu-id="92cf6-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
