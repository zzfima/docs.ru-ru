---
title: "Практическое руководство. Отображение данных с помощью GridViewRowPresenter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ebe0a47d38a2cfda2a7d150b4a3886d9f63ee190
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Практическое руководство. Отображение данных с помощью GridViewRowPresenter
В этом примере показано, как использовать <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов для отображения данных в столбцах.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать <xref:System.Windows.Controls.GridViewColumnCollection> , отображающий <xref:System.DateTime.DayOfWeek%2A> и <xref:System.DateTime.Year%2A> из <xref:System.DateTime> объектов с помощью <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов. В примере также определяется <xref:System.Windows.Style> для <xref:System.Windows.Controls.GridViewColumn.Header%2A> из <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewColumnCollection>  
 [Общие сведения о GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
