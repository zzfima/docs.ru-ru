---
title: Общие сведения об элементе управления ListView (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 7b7eac942a7e857ad731c0f77389e84aee287c08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952155"
---
# <a name="listview-control-overview-windows-forms"></a>Общие сведения об элементе управления ListView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.ListView> Windows Forms отображает список элементов со значками. Представление списка можно использовать для создания пользовательского интерфейса, аналогичного правой области окна проводника. Элемент управления имеет четыре режима представления: LargeIcon, маленькие значки, List и Details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Что можно сделать с помощью элемента управления ListView  
  
> [!NOTE]
> Дополнительный режим просмотра, плитка, доступен только в Windows XP и операционной системе Windows Server 2003. Дополнительные сведения см. в разделе [Практическое руководство. Включите мозаичное представление в Windows Forms элементе управления](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)ListView.  
  
 В режиме LargeIcon рядом с текстом элемента отображаются крупные значки. элементы отображаются в нескольких столбцах, если элемент управления достаточно большой. Режим маленькие значки одинаковый, за исключением того, что он отображает небольшие значки. Режим списка отображает небольшие значки, но всегда находится в одном столбце. В режиме подробностей отображаются элементы в нескольких столбцах. Подробную информацию см. в разделе [Практическое руководство. Добавьте столбцы в Windows Forms элемент управления](how-to-add-columns-to-the-windows-forms-listview-control.md)ListView. Режим просмотра определяется <xref:System.Windows.Forms.ListView.View%2A> свойством. Все режимы просмотра могут отображать изображения из списков изображений. Подробную информацию см. в разделе [Практическое руководство. Отображение значков для элемента управления](how-to-display-icons-for-the-windows-forms-listview-control.md)ListView Windows Forms.  
  
 В следующей таблице перечислены некоторые <xref:System.Windows.Forms.ListView> элементы и представления, которые они являются допустимыми.  
  
|Элемент ListView|Вид|  
|---------------------|----------|  
|Свойство <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Свойство <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Свойство <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Событие<xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View.Details>|  
|Метод <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>или <xref:System.Windows.Forms.View.Tile>|  
|Метод <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> или <xref:System.Windows.Forms.View.LargeIcon>|  
|Метод <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> или <xref:System.Windows.Forms.View.Tile>|  
|Свойство <xref:System.Windows.Forms.ListView.Groups%2A>|Все представления, Кроме<xref:System.Windows.Forms.View.List>|  
|Свойство <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Свойство <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>или <xref:System.Windows.Forms.View.Tile>|  
  
 Ключевым свойством <xref:System.Windows.Forms.ListView> элемента управления является <xref:System.Windows.Forms.ListView.Items%2A>, который содержит элементы, отображаемые элементом управления. <xref:System.Windows.Forms.ListView.SelectedItems%2A> Свойство содержит коллекцию элементов, выбранных в данный момент в элементе управления. Пользователь может выбрать несколько элементов, например, чтобы перетащить несколько элементов за раз в другой элемент управления, если <xref:System.Windows.Forms.ListView.MultiSelect%2A> свойство имеет `true`значение. Элемент управления может отображать флажки рядом с элементами, <xref:System.Windows.Forms.ListView.CheckBoxes%2A> если свойство имеет значение `true`. <xref:System.Windows.Forms.ListView>  
  
 Свойство определяет тип действия, которое пользователь должен предпринять для активации элемента в списке: <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>и <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ListView.Activation%2A> <xref:System.Windows.Forms.ItemActivation.OneClick>для активации элемента требуется одно нажатие кнопки. <xref:System.Windows.Forms.ItemActivation.TwoClick>Активация требует, чтобы пользователь дважды щелкнул элемент, чтобы активировать его. один щелчок изменяет цвет текста элемента. <xref:System.Windows.Forms.ItemActivation.Standard>Активация требует, чтобы пользователь дважды щелкнул, чтобы активировать элемент, но элемент не изменит внешний вид.  
  
 <xref:System.Windows.Forms.ListView> Элемент управления также поддерживает стили оформления и другие возможности, доступные на платформе Windows XP, включая группирование, мозаичное представление и метки вставки.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ListView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в Windows Forms элемент управления ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение значков для элемента управления ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Практическое руководство. Отображение подэлементов в столбцах с Windows Forms элементом управления ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Выбор элемента в элементе управления ListView Windows Forms](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Практическое руководство. Группирование элементов в элементе управления ListView Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Отображение метки вставки в элементе управления Windows Forms ListView](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Практическое руководство. Добавление возможностей поиска в элемент управления ListView](how-to-add-search-capabilities-to-a-listview-control.md)
- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Практическое руководство. Создание пользовательского интерфейса с несколькими панелями с помощью Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
