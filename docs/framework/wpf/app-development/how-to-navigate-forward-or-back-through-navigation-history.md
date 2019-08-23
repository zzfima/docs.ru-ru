---
title: Практическое руководство. Переход вперед или назад по журналу навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961348"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Практическое руководство. Переход вперед или назад по журналу навигации
В этом примере показано, как перейти вперед или назад к записям в журнале навигации.  
  
## <a name="example"></a>Пример  
 Код, запускаемый из содержимого на следующих узлах, может перемещаться вперед или назад через журнал навигации, по одной записи за раз.  
  
- <xref:System.Windows.Navigation.NavigationWindow>использующ<xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame>использующ<xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 Прежде чем можно будет перейти вперед к одной записи, необходимо сначала проверить наличие записей в журнале переходов вперед, проверив свойство **кангофорвард** . Для перехода вперед на одну запись вызывается метод **GoForward** . Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Прежде чем переходить к одной записи, необходимо сначала проверить наличие записей в журнале переходов назад, изучив свойство **CanGoBack** . Для перехода назад к одной записи вызывается метод **GoBack** . Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **Кангофорвард**, **GoForward**, **CanGoBack**и **GoBack** реализуются с помощью <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
> При вызове **GoForward**и отсутствии записей в журнале переходов вперед или при вызове программы **GoBack**и отсутствии записей в <xref:System.InvalidOperationException> журнале переходов назад создается исключение.
