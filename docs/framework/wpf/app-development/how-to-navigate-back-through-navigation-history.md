---
title: Практическое руководство. Переход назад по журналу навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817975"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Практическое руководство. Переход назад по журналу навигации
В этом примере показано, как перейти к записям в журнале обратной навигации.  
  
## <a name="example"></a>Пример  
 Код, который выполняется из содержимого, размещенного в <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> с помощью <xref:System.Windows.Navigation.NavigationService>или обозревателя Internet Explorer, может переходить назад по журналу переходов, по одной записи за раз.  
  
 Переход назад к одной записи требует сначала проверить наличие записей в журнале переходов назад, проверив свойство **CanGoBack** перед переходом назад по одной записи, вызвав метод **GoBack** . Это показано в следующем примере:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** и **GoBack** реализуются с помощью <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  При вызове программы **GoBack**и отсутствии записей в журнале переходов назад создается исключение <xref:System.InvalidOperationException> .
