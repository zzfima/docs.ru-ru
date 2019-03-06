---
title: Практическое руководство. Перейдите назад по журналу навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: c489a1593b3d1f22fe1ad6e648d3f8a3f7a6cd44
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377772"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="8a930-102">Практическое руководство. Перейдите назад по журналу навигации</span><span class="sxs-lookup"><span data-stu-id="8a930-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="8a930-103">В этом примере показано, как для перехода к записям журнала переходов.</span><span class="sxs-lookup"><span data-stu-id="8a930-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a930-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8a930-104">Example</span></span>  
 <span data-ttu-id="8a930-105">Код, выполняемый из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> с помощью <xref:System.Windows.Navigation.NavigationService>, или [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] можно перейти назад по журналу навигации, одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="8a930-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="8a930-106">Навигация влево на одну запись сначала требуется выполнить проверку, записи в журнале переходов назад, проверяя **CanGoBack** свойства, прежде чем переход назад на одну запись, вызвав **GoBack** метод.</span><span class="sxs-lookup"><span data-stu-id="8a930-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="8a930-107">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8a930-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="8a930-108">**CanGoBack** и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="8a930-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a930-109">При вызове метода **GoBack**, и нет записей в журнале переходов назад, <xref:System.InvalidOperationException> возникает.</span><span class="sxs-lookup"><span data-stu-id="8a930-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
