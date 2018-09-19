---
title: 'Практическое: перейти назад по журналу навигации'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 7266c9486524e962a859c34c9be5ab8f6d7bf7d5
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46322237"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Практическое: перейти назад по журналу навигации
В этом примере показано, как для перехода к записям журнала переходов.  
  
## <a name="example"></a>Пример  
 Код, выполняемый из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> с помощью <xref:System.Windows.Navigation.NavigationService>, или [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] можно перейти назад по журналу навигации, одной записи за раз.  
  
 Навигация влево на одну запись сначала требуется выполнить проверку, записи в журнале переходов назад, проверяя **CanGoBack** свойства, прежде чем переход назад на одну запись, вызвав **GoBack** метод. Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  При вызове метода **GoBack**, и нет записей в журнале переходов назад, <xref:System.InvalidOperationException> возникает.
