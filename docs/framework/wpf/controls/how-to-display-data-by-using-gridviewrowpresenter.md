---
title: Практическое руководство. Отображение данных с помощью GridViewRowPresenter
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: f05e1bd67d37d21a010562c7be5db5ca594f36db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369582"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Практическое руководство. Отображение данных с помощью GridViewRowPresenter
В этом примере показано, как использовать <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов для отображения данных в столбцах.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать <xref:System.Windows.Controls.GridViewColumnCollection> , отображающий <xref:System.DateTime.DayOfWeek%2A> и <xref:System.DateTime.Year%2A> из <xref:System.DateTime> объекта с помощью <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов. В примере также определяется <xref:System.Windows.Style> для <xref:System.Windows.Controls.GridViewColumn.Header%2A> из <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [Общие сведения о GridView](gridview-overview.md)
