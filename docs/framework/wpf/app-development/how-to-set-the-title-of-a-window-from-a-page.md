---
title: Практическое руководство. Задание заголовка окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940788"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="a147b-102">Практическое руководство. Задание заголовка окна из страницы</span><span class="sxs-lookup"><span data-stu-id="a147b-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="a147b-103">В этом примере показано, как задать заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.</span><span class="sxs-lookup"><span data-stu-id="a147b-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a147b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a147b-104">Example</span></span>  
 <span data-ttu-id="a147b-105">Страница может изменить заголовок окна, в котором он размещается, задав <xref:System.Windows.Controls.Page.WindowTitle%2A> свойство следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a147b-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <span data-ttu-id="a147b-106"><xref:System.Windows.Controls.Page.Title%2A> Установка свойства страницы не изменяет значение заголовка окна.</span><span class="sxs-lookup"><span data-stu-id="a147b-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="a147b-107">Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале навигации.</span><span class="sxs-lookup"><span data-stu-id="a147b-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
