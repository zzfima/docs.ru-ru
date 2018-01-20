---
title: "Общие сведения об элементе управления ListView (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b79fecb0a537f4c568b4a57e9ce2bfab8d8e1005
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="listview-control-overview-windows-forms"></a>Общие сведения об элементе управления ListView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms отображает список элементов со значками. Представление списка можно использовать для создания пользовательского интерфейса, аналогичного правой области окна проводника. Элемент управления имеет четыре режима представления: LargeIcon, SmallIcon, списка и сведений.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Что делать с элементом управления ListView  
  
> [!NOTE]
>  Дополнительный режим просмотра плитки, доступен только в Windows XP и Windows Server 2003 операционной системы. Дополнительные сведения см. в разделе [как: Включение вида мозаики в элементе управления ListView формы Windows](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 В режиме LargeIcon отображает крупные значки рядом с текстом элемента; элементы появляются в нескольких столбцах, если элемент управления является достаточно большим. Режимом SmallIcon одинаково за исключением того, что отображаются мелкие значки. Режим списка отображаются мелкие значки, но всегда находится в одном столбце. Сведения о режиме отображаются элементы в нескольких столбцах. Дополнительные сведения см. в разделе [как: Добавление столбцов в элемент управления Windows Forms ListView](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md). Режим просмотра определяется <xref:System.Windows.Forms.ListView.View%2A> свойство. Все режимы представления можно отображать изображения из списков изображений. Дополнительные сведения см. в разделе [как: отображение значков для элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 В следующей таблице перечислены некоторые из <xref:System.Windows.Forms.ListView> члены и представлений, они являются допустимыми в.  
  
|ListView-элемент|Просмотр|  
|---------------------|----------|  
|Свойство <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Свойство <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Свойство <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Событие <xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View.Details>|  
|Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>или <xref:System.Windows.Forms.View.Tile>|  
|Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Свойство <xref:System.Windows.Forms.ListView.Groups%2A>|Все представления, за исключением<xref:System.Windows.Forms.View.List>|  
|Свойство <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Свойство <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>или <xref:System.Windows.Forms.View.Tile>|  
  
 Ключевое свойство <xref:System.Windows.Forms.ListView> управления <xref:System.Windows.Forms.ListView.Items%2A>, который содержит элементы, отображаемые элементом управления. <xref:System.Windows.Forms.ListView.SelectedItems%2A> Свойство содержит коллекцию элементов, выбранных в данный момент в элементе управления. Пользователь может выбрать несколько элементов, например перетаскивание нескольких элементов одновременно на другой элемент управления, если <xref:System.Windows.Forms.ListView.MultiSelect%2A> свойству `true`. <xref:System.Windows.Forms.ListView> Элемент управления может отображать флажки рядом с элементами, если <xref:System.Windows.Forms.ListView.CheckBoxes%2A> свойству `true`.  
  
 <xref:System.Windows.Forms.ListView.Activation%2A> Свойство определяет, какой тип действия должен выполнить пользователь для активации элемента в списке: параметры <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, и <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick>для активации требуется одним щелчком для активации элемента. <xref:System.Windows.Forms.ItemActivation.TwoClick>Активация требует от пользователя, дважды щелкните для активации элемента; одним щелчком изменяет цвет текста элемента. <xref:System.Windows.Forms.ItemActivation.Standard>Активация требует от пользователя, щелкните дважды, чтобы активировать элемент, но элемент не изменяет внешний вид.  
  
 <xref:System.Windows.Forms.ListView> Управления также поддерживает визуальные стили и другие средства, доступные на платформе Windows XP, включая группирование, мозаичное представление и метки вставки. Дополнительные сведения см. в разделе [возможности Windows XP и элементы управления Windows Forms](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## <a name="see-also"></a>См. также  
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
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
