---
title: "Как: перейти назад по истории навигации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c715bda86fe6a4a010d80000db89619fc8bf8b7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Как: перейти назад по истории навигации
В этом примере показано, как перейти к записям журнала переходов.  
  
## <a name="example"></a>Пример  
 Код, который запускается из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> использовать <xref:System.Windows.Navigation.NavigationService>, или [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] можно перейти назад по истории навигации, одной записи за раз.  
  
 Навигация на одну запись требуется сначала проверить наличие записей в журнале переходов назад путем проверки **CanGoBack** свойства перед переходом назад на одну запись вызвать **GoBack** метод. Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** и **GoBack** реализуются <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, и <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  При вызове метода **GoBack**, и нет ни одной записи в журнале переходов назад <xref:System.InvalidOperationException> возникает.
