---
title: "Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Практическое руководство. Изменение порядка выравнивания столбцов в элементе управления ListView по горизонтали
По умолчанию содержимое каждого столбца в <xref:System.Windows.Controls.ListViewItem> по левому краю. Выравнивание каждого столбца можно изменить, указав <xref:System.Windows.DataTemplate> и параметр <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства элемента в пределах <xref:System.Windows.DataTemplate>. В этом разделе показано, как <xref:System.Windows.Controls.ListView> выравнивания содержимого по умолчанию и как изменить выравнивание один столбец в <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Пример  
 В следующем примере данные в `Title` и `ISBN` столбцы по левому краю.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Чтобы изменить выравнивание `ISBN` столбец, необходимо указать, что <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> каждого экземпляра <xref:System.Windows.Controls.ListViewItem> — <xref:System.Windows.HorizontalAlignment.Stretch>, после чего элементов в каждом <xref:System.Windows.Controls.ListViewItem> может охватывать или размещаться на всю ширину каждого столбца. Поскольку <xref:System.Windows.Controls.ListView> привязан к источнику данных, необходимо создать стиль, который задает <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Далее необходимо использовать <xref:System.Windows.DataTemplate> для отображения содержимого вместо <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойство. Для отображения `ISBN` каждого шаблона <xref:System.Windows.DataTemplate> может содержать только <xref:System.Windows.Controls.TextBlock> с его <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство <xref:System.Windows.HorizontalAlignment.Right>.  
  
 В следующем примере определяется стиль и <xref:System.Windows.DataTemplate> необходимо сделать `ISBN` по правому краю столбца и изменения <xref:System.Windows.Controls.GridViewColumn> ссылка <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Практическое руководство. Привязка к XML-данным с помощью XMLDataProvider и запросов XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
