---
title: "Как: перейти назад по истории навигации"
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
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c715bda86fe6a4a010d80000db89619fc8bf8b7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="a5242-102">Как: перейти назад по истории навигации</span><span class="sxs-lookup"><span data-stu-id="a5242-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="a5242-103">В этом примере показано, как перейти к записям журнала переходов.</span><span class="sxs-lookup"><span data-stu-id="a5242-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5242-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a5242-104">Example</span></span>  
 <span data-ttu-id="a5242-105">Код, который запускается из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> использовать <xref:System.Windows.Navigation.NavigationService>, или [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] можно перейти назад по истории навигации, одной записи за раз.</span><span class="sxs-lookup"><span data-stu-id="a5242-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="a5242-106">Навигация на одну запись требуется сначала проверить наличие записей в журнале переходов назад путем проверки **CanGoBack** свойства перед переходом назад на одну запись вызвать **GoBack** метод.</span><span class="sxs-lookup"><span data-stu-id="a5242-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="a5242-107">Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a5242-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="a5242-108">**CanGoBack** и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="a5242-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5242-109">При вызове метода **GoBack**, и нет ни одной записи в журнале переходов назад <xref:System.InvalidOperationException> возникает.</span><span class="sxs-lookup"><span data-stu-id="a5242-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
