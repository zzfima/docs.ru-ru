---
title: Общие сведения об элементе управления ListView
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 9308ff6646704d16b32669827a1f26bebf6958d8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745152"
---
# <a name="listview-control-overview-windows-forms"></a>Общие сведения об элементе управления ListView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms отображает список элементов со значками. Представление списка можно использовать для создания пользовательского интерфейса, аналогичного правой области окна проводника. Элемент управления имеет четыре режима представления: LargeIcon, маленькие значки, List и Details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Что можно сделать с помощью элемента управления ListView  
  
> [!NOTE]
> Дополнительный режим просмотра, плитка, доступен только в Windows XP и операционной системе Windows Server 2003. Дополнительные сведения см. в разделе [инструкции. Включение мозаичного представления в Windows Forms элементе управления ListView](how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 В режиме LargeIcon рядом с текстом элемента отображаются крупные значки. элементы отображаются в нескольких столбцах, если элемент управления достаточно большой. Режим маленькие значки одинаковый, за исключением того, что он отображает небольшие значки. Режим списка отображает небольшие значки, но всегда находится в одном столбце. В режиме подробностей отображаются элементы в нескольких столбцах. Дополнительные сведения см. в разделе [инструкции. Добавление столбцов в Windows Forms элемент управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md). Режим просмотра определяется свойством <xref:System.Windows.Forms.ListView.View%2A>. Все режимы просмотра могут отображать изображения из списков изображений. Дополнительные сведения см. [в разделе как отображать значки для элемента управления ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 В следующей таблице перечислены некоторые элементы <xref:System.Windows.Forms.ListView> и представления, которые они являются допустимыми.  
  
|Элемент ListView|Представление|  
|---------------------|----------|  
|Свойство <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> либо <xref:System.Windows.Forms.View.LargeIcon>|  
|Свойство <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> либо <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Свойство <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> либо <xref:System.Windows.Forms.View.Tile>|  
|Событие<xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View.Details>|  
|Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List> или <xref:System.Windows.Forms.View.Tile>|  
|Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> либо <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> либо <xref:System.Windows.Forms.View.Tile>|  
|Свойство <xref:System.Windows.Forms.ListView.Groups%2A>|Все представления, кроме <xref:System.Windows.Forms.View.List>|  
|Свойство <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Свойство <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.Tile>|  
  
 Ключевым свойством элемента управления <xref:System.Windows.Forms.ListView> является <xref:System.Windows.Forms.ListView.Items%2A>, который содержит элементы, отображаемые элементом управления. Свойство <xref:System.Windows.Forms.ListView.SelectedItems%2A> содержит коллекцию элементов, выбранных в данный момент в элементе управления. Пользователь может выбрать несколько элементов, например, чтобы перетащить несколько элементов за раз в другой элемент управления, если свойство <xref:System.Windows.Forms.ListView.MultiSelect%2A> имеет значение `true`. Элемент управления <xref:System.Windows.Forms.ListView> может отображать флажки рядом с элементами, если свойство <xref:System.Windows.Forms.ListView.CheckBoxes%2A> имеет значение `true`.  
  
 Свойство <xref:System.Windows.Forms.ListView.Activation%2A> определяет тип действия, которое пользователь должен предпринять для активации элемента в списке: параметры <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>и <xref:System.Windows.Forms.ItemActivation.TwoClick>. Активация <xref:System.Windows.Forms.ItemActivation.OneClick> требует одного щелчка, чтобы активировать элемент. Активация <xref:System.Windows.Forms.ItemActivation.TwoClick> требует, чтобы пользователь дважды щелкнул элемент, чтобы активировать его. один щелчок изменяет цвет текста элемента. <xref:System.Windows.Forms.ItemActivation.Standard> активации требуется, чтобы пользователь дважды щелкнул, чтобы активировать элемент, но элемент не изменит внешний вид.  
  
 Элемент управления <xref:System.Windows.Forms.ListView> также поддерживает стили оформления и другие возможности, доступные на платформе Windows XP, включая группирование, мозаичное представление и метки вставки.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Выделение строки элемента управления ListView в Windows Forms](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Добавление в элемент управления ListView возможностей поиска](how-to-add-search-capabilities-to-a-listview-control.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
