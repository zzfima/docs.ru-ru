---
title: Практическое руководство. Задание заголовка окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357512"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="a2595-102">Практическое руководство. Задание заголовка окна из страницы</span><span class="sxs-lookup"><span data-stu-id="a2595-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="a2595-103">В этом примере показано, как установить заголовок окна, в котором <xref:System.Windows.Controls.Page> размещается.</span><span class="sxs-lookup"><span data-stu-id="a2595-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2595-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a2595-104">Example</span></span>  
 <span data-ttu-id="a2595-105">Страница можно изменить заголовок окна, на котором размещается, задав <xref:System.Windows.Controls.Page.WindowTitle%2A> свойство, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a2595-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="a2595-106">Параметр <xref:System.Windows.Controls.Page.Title%2A> свойства страницы не приводит к изменению значения заголовка окна.</span><span class="sxs-lookup"><span data-stu-id="a2595-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="a2595-107">Вместо этого <xref:System.Windows.Controls.Page.Title%2A> указывает имя записи страницы в журнале переходов.</span><span class="sxs-lookup"><span data-stu-id="a2595-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
