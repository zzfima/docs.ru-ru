---
title: Как выполнить Перейдите на страницу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 7b76a12cbe6e1622e5624f5416abf24a4ca292a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536919"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="e9dd5-102">Как выполнить Перейдите на страницу</span><span class="sxs-lookup"><span data-stu-id="e9dd5-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="e9dd5-103">В этом примере показано несколько способов, в которых страницу можно перейти из <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9dd5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e9dd5-104">Example</span></span>  
 <span data-ttu-id="e9dd5-105">Существует возможность <xref:System.Windows.Navigation.NavigationWindow> для перехода к странице, с помощью одного из следующих:</span><span class="sxs-lookup"><span data-stu-id="e9dd5-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="e9dd5-106">Свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="e9dd5-107">метод <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> ;</span><span class="sxs-lookup"><span data-stu-id="e9dd5-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] <span data-ttu-id="e9dd5-108">может быть либо относительным или абсолютным.</span><span class="sxs-lookup"><span data-stu-id="e9dd5-108">can be either relative or absolute.</span></span> <span data-ttu-id="e9dd5-109">Дополнительные сведения см. в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd5-109">For more information, see [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9dd5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e9dd5-110">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
