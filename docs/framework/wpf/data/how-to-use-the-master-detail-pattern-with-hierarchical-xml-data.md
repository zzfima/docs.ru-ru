---
title: Практическое руководство. Использование шаблона "основной-подробности" с иерархическими данными XML
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733412"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Практическое руководство. Использование шаблона "основной-подробности" с иерархическими данными XML
В этом примере показано, как реализовать сценарий "основной/подробности" с XML-данными.  
  
## <a name="example"></a>Пример  
 Этот пример представляет собой версию XML-данных примера, обсуждаемого в разделе [Использование шаблона «основной/подробности» с иерархическими данными](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). В этом примере данные по`League.xml`ся из файла. Обратите внимание, что третий <xref:System.Windows.Controls.ListBox> элемент управления отслеживает изменения выбора во втором <xref:System.Windows.Controls.ListBox> путем привязки к его свойству <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.HierarchicalDataTemplate>
- [Разделы практического руководства](data-binding-how-to-topics.md)
