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
ms.openlocfilehash: ac3b8b71b6adf04d71cf35edbb042b82c57d8e1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546270"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Практическое руководство. Переход вперед или назад по журналу навигации
В этом примере показано, как перейти вперед или назад для записи в журнале навигации.  
  
## <a name="example"></a>Пример  
 Код, выполняемый из содержимого в следующие узлы можно перейти вперед или назад по истории навигации, одной записи за раз.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> С помощью <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> С помощью <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Прежде чем можно будет перейти вперед на одну запись, необходимо сначала записать отсутствии записей в журнале прямой навигации путем проверки **CanGoForward** свойство. Чтобы перейти вперед на одну запись, вызовите **GoForward** метод. Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Прежде чем можно переходить назад на одну запись, необходимо сначала записать отсутствии записей в журнале переходов назад путем проверки **CanGoBack** свойство. Чтобы перейти назад на одну запись, вызовите **GoBack** метод. Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  При вызове метода **GoForward**, и нет ни одной записи в журнал прямой навигации, или при вызове метода **GoBack**, и нет ни одной записи в журнале переходов назад <xref:System.InvalidOperationException> возникает исключение.
