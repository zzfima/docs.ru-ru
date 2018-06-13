---
title: 'Как: остановка загрузки страницы'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
ms.openlocfilehash: e5cd7d1b881b816636c3acdd4d33565304ca9b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545549"
---
# <a name="how-to-stop-a-page-from-loading"></a>Как: остановка загрузки страницы
В этом примере показано, как вызвать <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> способ остановки перехода к содержимому до завершения его загрузки.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> останавливает загрузку запрошенного содержимого, в результате чего <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> вызова события.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
