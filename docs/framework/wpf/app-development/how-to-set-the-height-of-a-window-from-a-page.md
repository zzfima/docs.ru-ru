---
title: 'Как: Установка высоты окна на странице'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: e25bc3cf2f5de01177f79f671390bac39875d079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546059"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="79c89-102">Как: Установка высоты окна на странице</span><span class="sxs-lookup"><span data-stu-id="79c89-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="79c89-103">В этом примере показано, как задать высоту окна из <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="79c89-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="79c89-104">Example</span></span>  
 <span data-ttu-id="79c89-105">Объект <xref:System.Windows.Controls.Page> можно задать высоту окна ее размещения, задав <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="79c89-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="79c89-106">Это свойство позволяет <xref:System.Windows.Controls.Page> не нужно точно знать тип окна, на котором размещен.</span><span class="sxs-lookup"><span data-stu-id="79c89-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79c89-107">Чтобы задать высоту окна с помощью <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> должен быть дочерним элементом окна.</span><span class="sxs-lookup"><span data-stu-id="79c89-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
