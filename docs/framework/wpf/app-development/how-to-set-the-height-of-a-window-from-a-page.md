---
title: Практическое руководство. Задание высоты окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007333"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="c3390-102">Практическое руководство. Задание высоты окна из страницы</span><span class="sxs-lookup"><span data-stu-id="c3390-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="c3390-103">В этом примере показано, как задать высоту окна из <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="c3390-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3390-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c3390-104">Example</span></span>  
 <span data-ttu-id="c3390-105">Объект <xref:System.Windows.Controls.Page> можно задать высоту окна ее размещения, задав <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3390-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="c3390-106">Это свойство позволяет <xref:System.Windows.Controls.Page> не были точно знать тип окна, на котором она размещена.</span><span class="sxs-lookup"><span data-stu-id="c3390-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3390-107">Чтобы задать высоту окна с помощью <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> должен быть дочерним элементом окна.</span><span class="sxs-lookup"><span data-stu-id="c3390-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
