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
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Практическое руководство. Задание высоты окна из страницы
В этом примере показано, как задать высоту окна из <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Controls.Page> можно задать высоту окна ее размещения, задав <xref:System.Windows.Controls.Page.WindowHeight%2A>. Это свойство позволяет <xref:System.Windows.Controls.Page> не были точно знать тип окна, на котором она размещена.  
  
> [!NOTE]
>  Чтобы задать высоту окна с помощью <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> должен быть дочерним элементом окна.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
