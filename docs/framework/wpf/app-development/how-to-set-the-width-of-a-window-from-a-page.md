---
title: 'Как: Установка ширины окна на странице'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: a0ae0e136e0b7f1cd2a2ec56455e14723e8fa306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545996"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Как: Установка ширины окна на странице
В этом примере показано, как задать ширину окна из <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Controls.Page> можно задать ширину окна ее размещения, задав <xref:System.Windows.Controls.Page.WindowWidth%2A>. Это свойство позволяет <xref:System.Windows.Controls.Page> не нужно точно знать тип окна, на котором размещен.  
  
> [!NOTE]
>  Чтобы задать ширину окна с помощью <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> должен быть дочерним элементом окна.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
