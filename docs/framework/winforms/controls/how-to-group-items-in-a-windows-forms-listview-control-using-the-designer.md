---
title: "Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5e86ecdad66c9e58d691b18126c1fbf782e3130
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора
Функция группирования элемента <xref:System.Windows.Forms.ListView> управления позволяет отображать соответствующие наборы элементов в группах. Эти группы разделяются на экране горизонтальными заголовками группы, содержащие заголовки групп. Можно использовать <xref:System.Windows.Forms.ListView> группы для упрощения просмотра больших списков, сгруппировав элементы по алфавиту, по датам или по другим критериям. На рисунке показаны некоторые сгруппированные элементы.  
  
 ![Группы ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Чтобы включить группирование, необходимо сначала создать один или несколько <xref:System.Windows.Forms.ListViewGroup> объектов в конструкторе или программным путем. После определения группы можно назначить элементы.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>группы доступны только на [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] при вызове приложением <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> метод. В предыдущих версиях операционных систем любой код, относящийся к группам, не действует, и группы не будут. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Чтобы добавить или удалить группы в конструкторе  
  
1.  В **свойства** окно, нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.ListView.Groups%2A> свойство.  
  
     **Редактор коллекции ListViewGroup** отображается.  
  
2.  Чтобы добавить группу, нажмите кнопку **добавить** кнопки. Затем можно задать свойства новой группы, такие как <xref:System.Windows.Forms.ListViewGroup.Header%2A> и <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> свойства. Чтобы удалить группу, выберите его и нажмите кнопку **удалить** кнопки.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Чтобы назначить элементы группам в конструкторе  
  
1.  В **свойства** окно, нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.ListView.Items%2A> свойство.  
  
     **Редактор коллекции ListViewItem** отображается.  
  
2.  Чтобы добавить новый элемент, щелкните **добавить** кнопки. Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListViewItem.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> свойства.  
  
3.  Выберите <xref:System.Windows.Forms.ListViewItem.Group%2A> свойство и выберите группу из раскрывающегося списка.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Возможности Windows XP и элементы управления Windows Forms](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
