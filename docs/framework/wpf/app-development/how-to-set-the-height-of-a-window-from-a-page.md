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
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Практическое руководство. Задание высоты окна из страницы
В этом примере показано, как задать высоту окна из <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Пример  
 Можно задать высоту главного окна, задав значение <xref:System.Windows.Controls.Page.WindowHeight%2A>. <xref:System.Windows.Controls.Page> Это свойство позволяет <xref:System.Windows.Controls.Page> не иметь явных сведений о типе окна, на котором оно размещается.  
  
> [!NOTE]
> Чтобы задать высоту окна с помощью <xref:System.Windows.Controls.Page.WindowHeight%2A>, элемент <xref:System.Windows.Controls.Page> должен быть дочерним по отношению к окну.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
