---
title: "Общие сведения об элементе управления ListView (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "представления списков"
  - "списки"
  - "ListView - элемент управления [Windows Forms], об элементе управления ListView"
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения об элементе управления ListView (Windows Forms)
В элементе управления Windows Forms <xref:System.Windows.Forms.ListView> отображается список элементов со значками.  Представление в виде списка может использоваться для создания пользовательского интерфейса, аналогичного правой области окна Windows Explorer.  Для этого элемента управления предусмотрено четыре режима представления: LargeIcon \(крупные значки\), SmallIcon \(мелкие значки\), List \(список\) и Details \(таблица\).  
  
## Возможные действия с элементом управления ListView  
  
> [!NOTE]
>  Дополнительный режим просмотра – Tile \(мозаичное представление\) – доступен только в операционных системах Windows XP и Windows Server 2003.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 В режиме LargeIcon рядом с текстом элементов отображаются крупные значки; если элемент управления достаточно большой, элементы появляются в нескольких столбцах.  Режим SmallIcon аналогичен предыдущему, за исключением того, что отображаются мелкие значки.  В режиме List отображаются мелкие значки, но всегда в одном столбце.  В режиме Details элементы отображаются в нескольких столбцах.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  Режим просмотра определяется свойством <xref:System.Windows.Forms.ListView.View%2A>.  Во всех режимах просмотра могут отображаться рисунки из списков рисунков.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 В следующей таблице перечислены некоторые из членов <xref:System.Windows.Forms.ListView> и представления, в которых они действуют.  
  
|Элемент ListView|Просмотр|  
|----------------------|--------------|  
|Свойство <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Свойство <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Метод <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View>|  
|Свойство <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Событие <xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View>|  
|Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Метод <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
|Свойство <xref:System.Windows.Forms.ListView.Groups%2A>|Все представления, кроме <xref:System.Windows.Forms.View>|  
|Свойство <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View>.|  
|Свойство <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> или <xref:System.Windows.Forms.View>|  
  
 Основным свойством элемента управления <xref:System.Windows.Forms.ListView> является свойство <xref:System.Windows.Forms.ListView.Items%2A>, содержащее элементы, отображаемые элементом управления.  Свойство <xref:System.Windows.Forms.ListView.SelectedItems%2A> содержит коллекцию элементов, выбранных в настоящий момент в элементе управления.  Если для свойства <xref:System.Windows.Forms.ListView.MultiSelect%2A> задано значение `true`, пользователь имеет возможность выбрать несколько элементов, например перетащить сразу несколько элементов в другой элемент управления.  Если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes%2A> задано значение `true`, в элементе управления <xref:System.Windows.Forms.ListView> рядом с элементами могут отображаться флажки.  
  
 Свойство <xref:System.Windows.Forms.ListView.Activation%2A> определяет тип действия, которое должен выполнить пользователь, чтобы активировать элемент в списке. Возможные варианты — <xref:System.Windows.Forms.ItemActivation>, <xref:System.Windows.Forms.ItemActivation> и <xref:System.Windows.Forms.ItemActivation>.  Активация <xref:System.Windows.Forms.ItemActivation> означает, что для активации элемента требуется сделать один щелчок.  Для активации <xref:System.Windows.Forms.ItemActivation> требуется, чтобы пользователь дважды щелкнул активируемый элемент; одиночный щелчок изменит цвет текста элемента.  Для активации <xref:System.Windows.Forms.ItemActivation> требуется, чтобы пользователь дважды щелкнул активируемый элемент, но внешний вид элемента при этом не изменяется.  
  
 Элемент управления <xref:System.Windows.Forms.ListView> также поддерживает визуальные стили и другие возможности, предоставляемые платформой Windows XP, включая группирование, мозаичное представление и метки вставки.  Дополнительные сведения см. в разделе [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ru-ru/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Практическое руководство. Выделение строки элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)   
 [Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)   
 [Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление в элемент управления ListView возможностей поиска](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)   
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)