---
title: "Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "группирование"
  - "группы, в элементах управления Windows Forms"
  - "ListView - элемент управления [Windows Forms], группирование элементов"
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора
Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать соответствующие наборы элементов в виде групп.  Эти группы разделяются на экране горизонтальными заголовками группы, которые содержат названия групп.  Можно использовать группы <xref:System.Windows.Forms.ListView> для упрощения просмотра больших списков за счет группирования их элементов по алфавиту, по дате или по другим критериям.  На приведенном ниже рисунке показаны некоторые сгруппированные элементы.  
  
 ![Группы ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Для разрешения группирования необходимо сначала создать один или несколько объектов <xref:System.Windows.Forms.ListViewGroup> в конструкторе или программным путем.  После определения группы можно назначить ее элементы.  
  
> [!NOTE]
>  Группы <xref:System.Windows.Forms.ListView> можно использовать только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] при вызове приложением метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  В предыдущих версиях операционных систем код, связанный с созданием групп, не действует, и группы отображаться не будут.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить или удалить группы в режиме конструктора, выполните следующие действия:  
  
1.  В окне **Свойства** нажмите кнопку с **многоточием** \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     Появится окно **Редактор коллекции ListViewGroup**.  
  
2.  Чтобы добавить группу, нажмите кнопку **Добавить**.  Затем можно задать свойства новой группы, например <xref:System.Windows.Forms.ListViewGroup.Header%2A> и <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.  Чтобы удалить группу, выделите ее и нажмите кнопку **Удалить**.  
  
### Чтобы назначить элементы группам в режиме конструктора, выполните следующие действия:  
  
1.  В окне **Свойства** нажмите кнопку с **многоточием** \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     Появится окно **Редактор коллекции ListViewItem**.  
  
2.  Чтобы добавить новый элемент, нажмите кнопку **Добавить**.  Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListViewItem.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.  
  
3.  Выберите свойство <xref:System.Windows.Forms.ListViewItem.Group%2A>, затем выберите группу из раскрывающегося списка.  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ru-ru/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)