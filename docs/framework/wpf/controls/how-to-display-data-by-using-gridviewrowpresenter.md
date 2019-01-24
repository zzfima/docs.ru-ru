---
title: Как выполнить Отображение данных с помощью GridViewRowPresenter
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: b60fe0e78883b166688377c42113a093c78d7751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607963"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="02a2c-102">Как выполнить Отображение данных с помощью GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="02a2c-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="02a2c-103">В этом примере показано, как использовать <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов для отображения данных в столбцах.</span><span class="sxs-lookup"><span data-stu-id="02a2c-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02a2c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="02a2c-104">Example</span></span>  
 <span data-ttu-id="02a2c-105">В следующем примере показано, как указать <xref:System.Windows.Controls.GridViewColumnCollection> , отображающий <xref:System.DateTime.DayOfWeek%2A> и <xref:System.DateTime.Year%2A> из <xref:System.DateTime> объекта с помощью <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> объектов.</span><span class="sxs-lookup"><span data-stu-id="02a2c-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="02a2c-106">В примере также определяется <xref:System.Windows.Style> для <xref:System.Windows.Controls.GridViewColumn.Header%2A> из <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="02a2c-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="02a2c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="02a2c-107">See also</span></span>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="02a2c-108">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="02a2c-108">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
