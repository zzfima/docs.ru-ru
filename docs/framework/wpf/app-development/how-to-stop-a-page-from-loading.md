---
title: Практическое руководство. Остановка загрузки страницы
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
ms.openlocfilehash: c5694bb2cb6c618cd84bad3dc893ae3855e44892
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357850"
---
# <a name="how-to-stop-a-page-from-loading"></a><span data-ttu-id="9c6f0-102">Практическое руководство. Остановка загрузки страницы</span><span class="sxs-lookup"><span data-stu-id="9c6f0-102">How to: Stop a Page from Loading</span></span>
<span data-ttu-id="9c6f0-103">В этом примере показан способ вызова <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> метод навигации к содержимому до завершения загрузки.</span><span class="sxs-lookup"><span data-stu-id="9c6f0-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> method to stop navigation to content before it has finished being downloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c6f0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9c6f0-104">Example</span></span>  
 <span data-ttu-id="9c6f0-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> останавливает загрузку запрошенного содержимого и вызывает <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> возникает событие.</span><span class="sxs-lookup"><span data-stu-id="9c6f0-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> stops the download of the requested content, and causes the <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> event to be raised.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
