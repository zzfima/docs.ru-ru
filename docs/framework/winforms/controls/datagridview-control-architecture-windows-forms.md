---
title: "Архитектура элементов управления DataGridView (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb44a32e63fd7a0ff0e480c205d5459da2ce2bd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-architecture-windows-forms"></a>Архитектура элементов управления DataGridView (Windows Forms)
<xref:System.Windows.Forms.DataGridView> Управления и его связанные классы предназначены для гибкую расширяемую систему для отображения и изменения табличных данных. Эти классы содержатся в <xref:System.Windows.Forms?displayProperty=nameWithType> пространства имен и они именуются с префиксом «DataGridView».  
  
## <a name="architecture-elements"></a>Элементы архитектуры  
 Основной <xref:System.Windows.Forms.DataGridView> сопутствующих классов являются производными от <xref:System.Windows.Forms.DataGridViewElement>. Следующей объектной модели показано <xref:System.Windows.Forms.DataGridViewElement> иерархии наследования.  
  
 ![Объектная модель DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")  
Объектная модель DataGridViewElement  
  
 <xref:System.Windows.Forms.DataGridViewElement> Класс предоставляет ссылку на родительский объект <xref:System.Windows.Forms.DataGridView> управления и имеет <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство, которое содержит значение, которое представляет сочетание значений из <xref:System.Windows.Forms.DataGridViewElementStates> перечисления.  
  
 В следующих разделах описаны <xref:System.Windows.Forms.DataGridView> сопутствующих классов более подробно.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> Перечисление содержит следующие значения:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 Значения этого перечисления могут объединяться с побитовые логические операторы, поэтому <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойства можно выразить несколько состояний одновременно. Например <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, и <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Ячейки и зоны  
 <xref:System.Windows.Forms.DataGridView> Управления состоит из двух основных типов объектов: ячеек и зон. Все ячейки являются производными от <xref:System.Windows.Forms.DataGridViewCell> базового класса. Два вида делений, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>, оба являются производными от <xref:System.Windows.Forms.DataGridViewBand> базового класса.  
  
 <xref:System.Windows.Forms.DataGridView> Управления взаимодействует с несколькими классами, но чаще всего встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, и <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 Ячейка является базовой единицей взаимодействия для <xref:System.Windows.Forms.DataGridView>. Отображение выравнивается по центру ячейки и ввода данных часто осуществляется с помощью ячеек. Доступ к ячейкам с помощью <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> коллекцию <xref:System.Windows.Forms.DataGridViewRow> класса и имеют доступ к выбранным ячейкам с помощью <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> коллекцию <xref:System.Windows.Forms.DataGridView> элемента управления. В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewCell> иерархии наследования.  
  
 ![Объектная модель DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")  
Объектная модель DataGridViewCell  
  
 <xref:System.Windows.Forms.DataGridViewCell> Тип является абстрактным базовым классом, от которого наследуют все типы ячеек. <xref:System.Windows.Forms.DataGridViewCell>и его производные типы не являются элементы управления Windows Forms, но некоторые элементы управления ведущего приложения Windows Forms. Любые изменения функциональных возможностей, поддерживаемых ячейки обычно обрабатываются размещенного элемента управления.  
  
 <xref:System.Windows.Forms.DataGridViewCell>объекты контролирует собственные внешним видом и оформлением так же как элементы управления Windows Forms. Вместо этого <xref:System.Windows.Forms.DataGridView> отвечает за внешний вид его <xref:System.Windows.Forms.DataGridViewCell> объектов. Вы может существенно повлиять на внешний вид и поведение ячеек, взаимодействуя с <xref:System.Windows.Forms.DataGridView> свойства и события для элемента управления. При наличии особых требований к настройкам, выходящих за рамки возможностей <xref:System.Windows.Forms.DataGridView> управления, можно реализовать собственный класс, производный от <xref:System.Windows.Forms.DataGridViewCell> или один из его дочерних классов.  
  
 В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewCell>:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   Пользовательские типы ячеек  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 Схема <xref:System.Windows.Forms.DataGridView> элемента управления хранилища данных представляется в формате <xref:System.Windows.Forms.DataGridView> столбцов элемента управления. Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> столбцов элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Columns%2A> коллекции. Выбранные столбцы доступны с помощью <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> коллекции. В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewColumn> иерархии наследования.  
  
 ![Объектная модель DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")  
Объектная модель DataGridViewColumn  
  
 Некоторые типы ключей ячейки имеют соответствующие типы столбцов. Они являются производными <xref:System.Windows.Forms.DataGridViewColumn> базового класса.  
  
 В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Пользовательские типы столбцов  
  
### <a name="datagridview-editing-controls"></a>Элементы управления редактирования DataGridView  
 Ячейки, поддерживающие расширенные функции редактирования, обычно используют размещенного элемента управления, который является производным от элемента управления Windows Forms. Эти элементы управления также реализовать <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейса. В следующей объектной модели показано использование этих элементов управления.  
  
 ![Объектная модель элемента управления редактирования DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")  
Объектная модель редактирования элемента управления DataGridView  
  
 Следующие элементы управления для редактирования, предоставляемых с <xref:System.Windows.Forms.DataGridView> управления:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Сведения о создании собственных редактирования элементов управления см. в разделе [как: элементы управления ведущего приложения в ячеек элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 В следующей таблице показаны отношения между типов ячеек, типы столбцов и элементами управления.  
  
|Тип ячейки|Размещаемый элемент управления|Тип столбца|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|Н/Д|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|Н/Д|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|Н/Д|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|Н/Д|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 <xref:System.Windows.Forms.DataGridViewRow> Хранения класс отображает поля данных записи из данных, к которому <xref:System.Windows.Forms.DataGridView> присоединенного элемента управления. Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> строк элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции. Выбранные строки доступны с помощью <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> коллекции. В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewRow> иерархии наследования.  
  
 ![Объектная модель DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")  
Объектная модель DataGridViewRow  
  
 Можно создавать производные типы из <xref:System.Windows.Forms.DataGridViewRow> класса, хотя это обычно не требуется. <xref:System.Windows.Forms.DataGridView> Управления имеет несколько связанных со строками событий и свойств для настройки поведения его <xref:System.Windows.Forms.DataGridViewRow> объектов.  
  
 При включении <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> , специальную строку для добавления новых строк отображается в виде последней строки. Эта строка является частью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции, но он имеет специальные функции, которые могут потребовать вашего внимания. Дополнительные сведения см. в разделе [с помощью строки для новых записей в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
