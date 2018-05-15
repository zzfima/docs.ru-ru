---
title: 'Как: перейдите на страницу'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 896287376979d40816e3937fff77b38bf71a62f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="df695-102">Как: перейдите на страницу</span><span class="sxs-lookup"><span data-stu-id="df695-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="df695-103">В этом примере показано несколько способов, в которых страницу можно перейти из <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="df695-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df695-104">Пример</span><span class="sxs-lookup"><span data-stu-id="df695-104">Example</span></span>  
 <span data-ttu-id="df695-105">Существует возможность <xref:System.Windows.Navigation.NavigationWindow> для перехода к странице с помощью одного из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="df695-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="df695-106">Свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="df695-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="df695-107">метод <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A>;</span><span class="sxs-lookup"><span data-stu-id="df695-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]<span data-ttu-id="df695-108"> может быть относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="df695-108"> can be either relative or absolute.</span></span> <span data-ttu-id="df695-109">Дополнительные сведения см. в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="df695-109">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df695-110">См. также</span><span class="sxs-lookup"><span data-stu-id="df695-110">See Also</span></span>  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>
