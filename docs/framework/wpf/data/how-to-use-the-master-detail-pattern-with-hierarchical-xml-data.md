---
title: Практическое руководство. Использование шаблона "Основной/подробности" с иерархическими XML-данными
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: ba6c932f519ffa5c3c70ecb21eb9b5d08c40fb28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086264"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="5fd50-102">Практическое руководство. Использование шаблона "Основной/подробности" с иерархическими XML-данными</span><span class="sxs-lookup"><span data-stu-id="5fd50-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="5fd50-103">В этом примере показано, как реализовать сценарий "основной / подробности" с [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных.</span><span class="sxs-lookup"><span data-stu-id="5fd50-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fd50-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5fd50-104">Example</span></span>  
 <span data-ttu-id="5fd50-105">Данный пример является [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] версию данных в примере, рассмотренном в [использование шаблона «основной-подробности» с иерархическими данными](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="5fd50-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="5fd50-106">В этом примере данные берутся из файла `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="5fd50-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="5fd50-107">Обратите внимание как третий <xref:System.Windows.Controls.ListBox> управления отслеживает изменения выделения во втором <xref:System.Windows.Controls.ListBox> путем привязки к его <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5fd50-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="5fd50-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5fd50-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="5fd50-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="5fd50-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
