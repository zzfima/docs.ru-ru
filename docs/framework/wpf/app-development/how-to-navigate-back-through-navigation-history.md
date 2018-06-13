---
title: 'Как: перейти назад по истории навигации'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 9acbc5d3388a8df0ec7d7b5326f449f092f0cb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546679"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="3a3dc-102">Как: перейти назад по истории навигации</span><span class="sxs-lookup"><span data-stu-id="3a3dc-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="3a3dc-103">В этом примере показано, как перейти к записям журнала переходов.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a3dc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3a3dc-104">Example</span></span>  
 <span data-ttu-id="3a3dc-105">Код, который запускается из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> использовать <xref:System.Windows.Navigation.NavigationService>, или [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] можно перейти назад по истории навигации, одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="3a3dc-106">Навигация на одну запись требуется сначала проверить наличие записей в журнале переходов назад путем проверки **CanGoBack** свойства перед переходом назад на одну запись вызвать **GoBack** метод.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="3a3dc-107">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3a3dc-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="3a3dc-108">**CanGoBack** и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a3dc-109">При вызове метода **GoBack**, и нет ни одной записи в журнале переходов назад <xref:System.InvalidOperationException> возникает.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
