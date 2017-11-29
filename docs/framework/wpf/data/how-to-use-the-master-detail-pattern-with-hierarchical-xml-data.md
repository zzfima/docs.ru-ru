---
title: "Практическое руководство. Использование шаблона \"основной-подробности\" с иерархическими данными XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b28a2220b5fc86654fe054deb9180450025f72f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="4051a-102">Практическое руководство. Использование шаблона "основной-подробности" с иерархическими данными XML</span><span class="sxs-lookup"><span data-stu-id="4051a-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="4051a-103">В этом примере показано, как для реализации сценария "главный подчиненный" с [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных.</span><span class="sxs-lookup"><span data-stu-id="4051a-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4051a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4051a-104">Example</span></span>  
 <span data-ttu-id="4051a-105">Данный пример является [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] версия данных примера, рассмотренного в [использовать шаблон «основной-подробности» с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="4051a-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="4051a-106">В этом примере данные поступают из файла `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="4051a-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="4051a-107">Обратите внимание как третья <xref:System.Windows.Controls.ListBox> управления отслеживает изменения выделения во втором <xref:System.Windows.Controls.ListBox> путем привязки к его <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4051a-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="4051a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4051a-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="4051a-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="4051a-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
