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
ms.workload: dotnet
ms.openlocfilehash: f0ef460664b3701f4942b8c28b8e39f891d7c871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="fadfc-102">Практическое руководство. Использование шаблона "основной-подробности" с иерархическими данными XML</span><span class="sxs-lookup"><span data-stu-id="fadfc-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="fadfc-103">В этом примере показано, как для реализации сценария "главный подчиненный" с [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных.</span><span class="sxs-lookup"><span data-stu-id="fadfc-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fadfc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fadfc-104">Example</span></span>  
 <span data-ttu-id="fadfc-105">Данный пример является [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] версия данных примера, рассмотренного в [использовать шаблон «основной-подробности» с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="fadfc-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="fadfc-106">В этом примере данные поступают из файла `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="fadfc-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="fadfc-107">Обратите внимание как третья <xref:System.Windows.Controls.ListBox> управления отслеживает изменения выделения во втором <xref:System.Windows.Controls.ListBox> путем привязки к его <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="fadfc-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="fadfc-108">См. также</span><span class="sxs-lookup"><span data-stu-id="fadfc-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="fadfc-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="fadfc-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
