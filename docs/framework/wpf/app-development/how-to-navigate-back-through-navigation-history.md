---
title: Практическое руководство. Переход назад по журналу навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969352"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="0d33b-102">Практическое руководство. Переход назад по журналу навигации</span><span class="sxs-lookup"><span data-stu-id="0d33b-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="0d33b-103">В этом примере показано, как перейти к записям в журнале обратной навигации.</span><span class="sxs-lookup"><span data-stu-id="0d33b-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d33b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0d33b-104">Example</span></span>  
 <span data-ttu-id="0d33b-105">Код, который выполняется из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> с помощью <xref:System.Windows.Navigation.NavigationService>или обозревателя Internet Explorer, может переходить назад по журналу переходов, по одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="0d33b-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="0d33b-106">Переход назад к одной записи требует сначала проверить наличие записей в журнале переходов назад, проверив свойство **CanGoBack** перед переходом назад по одной записи, вызвав метод **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="0d33b-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="0d33b-107">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0d33b-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="0d33b-108">**CanGoBack** и **GoBack** реализуются с помощью <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="0d33b-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d33b-109">При вызове программы **GoBack**и отсутствии записей в журнале переходов назад создается исключение <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="0d33b-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
