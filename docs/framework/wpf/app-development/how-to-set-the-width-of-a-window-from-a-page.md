---
title: Практическое руководство. Задание ширины окна из страницы
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940778"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Практическое руководство. Задание ширины окна из страницы
В этом примере показано, как задать ширину окна из <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Пример  
 Можно задать ширину главного окна, задав <xref:System.Windows.Controls.Page.WindowWidth%2A>. <xref:System.Windows.Controls.Page> Это свойство позволяет <xref:System.Windows.Controls.Page> не иметь явных сведений о типе окна, на котором оно размещается.  
  
> [!NOTE]
> Чтобы задать ширину окна с помощью <xref:System.Windows.Controls.Page.WindowWidth%2A>, элемент <xref:System.Windows.Controls.Page> должен быть дочерним по отношению к окну.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
