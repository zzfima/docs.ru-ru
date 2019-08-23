---
title: Практическое руководство. Задание высоты окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940801"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="84dfb-102">Практическое руководство. Задание высоты окна из страницы</span><span class="sxs-lookup"><span data-stu-id="84dfb-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="84dfb-103">В этом примере показано, как задать высоту окна из <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="84dfb-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84dfb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="84dfb-104">Example</span></span>  
 <span data-ttu-id="84dfb-105">Можно задать высоту главного окна, задав значение <xref:System.Windows.Controls.Page.WindowHeight%2A>. <xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="84dfb-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="84dfb-106">Это свойство позволяет <xref:System.Windows.Controls.Page> не иметь явных сведений о типе окна, на котором оно размещается.</span><span class="sxs-lookup"><span data-stu-id="84dfb-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84dfb-107">Чтобы задать высоту окна с помощью <xref:System.Windows.Controls.Page.WindowHeight%2A>, элемент <xref:System.Windows.Controls.Page> должен быть дочерним по отношению к окну.</span><span class="sxs-lookup"><span data-stu-id="84dfb-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
