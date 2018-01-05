---
title: "Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="6e208-102">Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали</span><span class="sxs-lookup"><span data-stu-id="6e208-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="6e208-103">По умолчанию содержимое каждого столбца в <xref:System.Windows.Controls.ListViewItem> по левому краю.</span><span class="sxs-lookup"><span data-stu-id="6e208-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="6e208-104">Выравнивание каждого столбца можно изменить, указав <xref:System.Windows.DataTemplate> и параметр <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства элемента в пределах <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="6e208-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="6e208-105">В этом разделе показано, как <xref:System.Windows.Controls.ListView> выравнивания содержимого по умолчанию и как изменить выравнивание один столбец в <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6e208-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e208-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6e208-106">Example</span></span>  
 <span data-ttu-id="6e208-107">В следующем примере данные в `Title` и `ISBN` столбцы по левому краю.</span><span class="sxs-lookup"><span data-stu-id="6e208-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="6e208-108">Чтобы изменить выравнивание `ISBN` столбец, необходимо указать, что <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> каждого экземпляра <xref:System.Windows.Controls.ListViewItem> — <xref:System.Windows.HorizontalAlignment.Stretch>, после чего элементов в каждом <xref:System.Windows.Controls.ListViewItem> может охватывать или размещаться на всю ширину каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="6e208-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="6e208-109">Поскольку <xref:System.Windows.Controls.ListView> привязан к источнику данных, необходимо создать стиль, который задает <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="6e208-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="6e208-110">Далее необходимо использовать <xref:System.Windows.DataTemplate> для отображения содержимого вместо <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="6e208-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="6e208-111">Для отображения `ISBN` каждого шаблона <xref:System.Windows.DataTemplate> может содержать только <xref:System.Windows.Controls.TextBlock> с его <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="6e208-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="6e208-112">В следующем примере определяется стиль и <xref:System.Windows.DataTemplate> необходимо сделать `ISBN` по правому краю столбца и изменения <xref:System.Windows.Controls.GridViewColumn> ссылка <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="6e208-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6e208-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6e208-113">See Also</span></span>  
 [<span data-ttu-id="6e208-114">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="6e208-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6e208-115">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="6e208-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="6e208-116">Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath</span><span class="sxs-lookup"><span data-stu-id="6e208-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="6e208-117">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="6e208-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
