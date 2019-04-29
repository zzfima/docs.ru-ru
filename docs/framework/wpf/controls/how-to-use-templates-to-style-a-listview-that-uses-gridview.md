---
title: Практическое руководство. Использование шаблонов для задания стиля ListView, использующего GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699127"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="244bb-102">Практическое руководство. Использование шаблонов для задания стиля ListView, использующего GridView</span><span class="sxs-lookup"><span data-stu-id="244bb-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="244bb-103">В этом примере показано, как использовать <xref:System.Windows.DataTemplate> и <xref:System.Windows.Style> объектов для определения внешнего вида <xref:System.Windows.Controls.ListView> элемента управления, использующего <xref:System.Windows.Controls.GridView> режим просмотра.</span><span class="sxs-lookup"><span data-stu-id="244bb-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="244bb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="244bb-104">Example</span></span>  
 <span data-ttu-id="244bb-105">В приведенных ниже примерах <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объекты, которые настраивать внешний вид заголовка столбца для <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="244bb-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="244bb-106">В следующем примере показано, как использовать эти <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объекты для установки <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> свойства <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="244bb-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="244bb-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Свойство определяет содержимое ячейки столбца.</span><span class="sxs-lookup"><span data-stu-id="244bb-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="244bb-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> И <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> только два из нескольких свойств, которые можно использовать для настройки внешнего вида заголовка столбца для <xref:System.Windows.Controls.GridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="244bb-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="244bb-109">Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="244bb-109">For more information, see [GridView Column Header Styles and Templates Overview](gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="244bb-110">В следующем примере показано определение <xref:System.Windows.DataTemplate> , настраивает внешний вид ячеек в <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="244bb-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="244bb-111">В следующем примере показано, как использовать этот <xref:System.Windows.DataTemplate> для определения содержимого <xref:System.Windows.Controls.GridViewColumn> ячейки.</span><span class="sxs-lookup"><span data-stu-id="244bb-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="244bb-112">Этот шаблон используется вместо <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойство, которое показано в предыдущем <xref:System.Windows.Controls.GridViewColumn> пример.</span><span class="sxs-lookup"><span data-stu-id="244bb-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="244bb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="244bb-113">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="244bb-114">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="244bb-114">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="244bb-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="244bb-115">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="244bb-116">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="244bb-116">ListView Overview</span></span>](listview-overview.md)
