---
title: Практическое руководство. Перейдите на страницу
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: a5a0e7a8e7effac7c51f4dee92d30de56d60d90c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369348"
---
# <a name="how-to-navigate-to-a-page"></a>Практическое руководство. Перейдите на страницу
В этом примере показано несколько способов, в которых страницу можно перейти из <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Пример  
 Существует возможность <xref:System.Windows.Navigation.NavigationWindow> для перехода к странице, с помощью одного из следующих:  
  
-   Свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.  
  
-   метод <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> ;  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] может быть либо относительным или абсолютным. Дополнительные сведения см. в разделе [URI типа "pack" в WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
