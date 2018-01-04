---
title: "Практическое руководство. Отображение содержимого ListView с помощью GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee2885868c07b00f16290b6414e7f7bdd64fd68c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Практическое руководство. Отображение содержимого ListView с помощью GridView
В этом примере показан способ определения <xref:System.Windows.Controls.GridView> режим просмотра для <xref:System.Windows.Controls.ListView> элемента управления.  
  
## <a name="example"></a>Пример  
 Можно определить режим просмотра для <xref:System.Windows.Controls.GridView> , указав <xref:System.Windows.Controls.GridViewColumn> объектов. В следующем примере показан способ определения <xref:System.Windows.Controls.GridViewColumn> объектов, которые привязаны к содержимому данных, указанный для <xref:System.Windows.Controls.ListView> элемента управления. Это <xref:System.Windows.Controls.GridView> примере задаются три <xref:System.Windows.Controls.GridViewColumn> объектов, которые сопоставляются `FirstName`, `LastName`, и `EmployeeNumber` поля `EmployeeInfoDataSource` задан в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> из <xref:System.Windows.Controls.ListView> элемента управления.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Ниже показано, как выглядит в этом примере.  
  
 ![ListView с выходными данными GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
