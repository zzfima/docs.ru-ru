---
title: Архитектура элементов управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742524"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Архитектура элементов управления DataGridView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.DataGridView> и связанные с ним классы разработаны как гибкая расширяемая система для отображения и редактирования табличных данных. Все эти классы содержатся в пространстве имен <xref:System.Windows.Forms?displayProperty=nameWithType> и все они называются префиксом "DataGridView".  
  
## <a name="architecture-elements"></a>Элементы архитектуры  
 Основные <xref:System.Windows.Forms.DataGridView>ные классы являются производными от <xref:System.Windows.Forms.DataGridViewElement>. Следующая объектная модель иллюстрирует иерархию наследования <xref:System.Windows.Forms.DataGridViewElement>.  
  
 ![Схема, на которой показана иерархия объектной модели Датагридвиевелемент.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 Класс <xref:System.Windows.Forms.DataGridViewElement> предоставляет ссылку на родительский элемент управления <xref:System.Windows.Forms.DataGridView> и имеет свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A>, которое содержит значение, представляющее сочетание значений перечисления <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
 В следующих разделах более подробно описаны сопутствующие классы <xref:System.Windows.Forms.DataGridView>.  
  
### <a name="datagridviewelementstates"></a>датагридвиевелементстатес  
 Перечисление <xref:System.Windows.Forms.DataGridViewElementStates> имеет такие значения:  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 Значения этого перечисления можно сочетать с побитовыми логическими операторами, поэтому свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A> может одновременно выразить несколько состояний. Например, <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>и <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Ячейки и полосы  
 Элемент управления <xref:System.Windows.Forms.DataGridView> состоит из двух фундаментальных типов объектов: ячеек и делений. Все ячейки являются производными от базового класса <xref:System.Windows.Forms.DataGridViewCell>. Два типа полос, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>, являются производными от базового класса <xref:System.Windows.Forms.DataGridViewBand>.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> взаимодействует с несколькими классами, но наиболее часто встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>и <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 Ячейка является основной единицей взаимодействия для <xref:System.Windows.Forms.DataGridView>. Дисплей выравнивается по ячейкам, а ввод данных часто выполняется через ячейки. Доступ к ячейкам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> класса <xref:System.Windows.Forms.DataGridViewRow>, а также получить доступ к выбранным ячейкам с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> элемента управления <xref:System.Windows.Forms.DataGridView>. В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewCell>.  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 Тип <xref:System.Windows.Forms.DataGridViewCell> является абстрактным базовым классом, от которого наследуются все типы ячеек. <xref:System.Windows.Forms.DataGridViewCell> и его производные типы не Windows Forms элементы управления, но некоторые элементы управления ведущего Windows Forms. Любая функция редактирования, поддерживаемая ячейкой, обычно обрабатывается размещаемым элементом управления.  
  
 <xref:System.Windows.Forms.DataGridViewCell> объекты не управляют собственными функциями внешнего вида и рисования так же, как Windows Forms элементами управления. Вместо этого <xref:System.Windows.Forms.DataGridView> отвечает за внешний вид объектов <xref:System.Windows.Forms.DataGridViewCell>. Можно значительно повлиять на внешний вид и поведение ячеек, взаимодействуя со свойствами и событиями элемента управления <xref:System.Windows.Forms.DataGridView>. При наличии особых требований к настройкам, которые выходят за пределы возможностей элемента управления <xref:System.Windows.Forms.DataGridView>, можно реализовать собственный класс, производный от <xref:System.Windows.Forms.DataGridViewCell> или одного из его дочерних классов.  
  
 В следующем списке показаны классы, производные от <xref:System.Windows.Forms.DataGridViewCell>:  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- Пользовательские типы ячеек  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 Схема присоединенного к <xref:System.Windows.Forms.DataGridView> элемента управления хранилища данных выражается в столбцах элемента управления <xref:System.Windows.Forms.DataGridView>. Доступ к столбцам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>. Доступ к выбранным столбцам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 Некоторые типы ключевых ячеек имеют соответствующие типы столбцов. Они являются производными от базового класса <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 В следующем списке показаны классы, производные от <xref:System.Windows.Forms.DataGridViewColumn>:  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- Пользовательские типы столбцов  
  
### <a name="datagridview-editing-controls"></a>Элементы управления редактированием DataGridView  
 Ячейки, поддерживающие расширенные функции редактирования, обычно используют размещенный элемент управления, производный от элемента управления Windows Forms. Эти элементы управления также реализуют интерфейс <xref:System.Windows.Forms.IDataGridViewEditingControl>. Следующая объектная модель иллюстрирует использование этих элементов управления.  
  
 ![Схема, показывающая иерархию модели объектов элемента управления редактированием DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 Следующие элементы управления для редактирования предоставляются с помощью элемента управления <xref:System.Windows.Forms.DataGridView>:  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Сведения о создании собственных элементов управления редактирования см. [в разделе как размещать элементы управления в Windows Forms ячейках DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 В следующей таблице показана связь между типами ячеек, типами столбцов и элементами управления для редактирования.  
  
|Тип ячейки|Размещенный элемент управления|Тип столбца|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|Недоступно|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|Недоступно|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|Недоступно|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|Недоступно|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 Класс <xref:System.Windows.Forms.DataGridViewRow> отображает поля данных записи из хранилища данных, к которому присоединен элемент управления <xref:System.Windows.Forms.DataGridView>. Доступ к строкам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>. Доступ к выбранным строкам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewRow>.  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 Вы можете создавать собственные типы из класса <xref:System.Windows.Forms.DataGridViewRow>, хотя это и не обязательно. Элемент управления <xref:System.Windows.Forms.DataGridView> имеет несколько связанных с строками событий и свойств для настройки поведения его <xref:System.Windows.Forms.DataGridViewRow> объектов.  
  
 Если включить свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> <xref:System.Windows.Forms.DataGridView> элемента управления, то в качестве последней строки появится специальная строка для добавления новых строк. Эта строка является частью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции, но она имеет специальные функции, которые могут потребовать вашего внимания. Дополнительные сведения см. в разделе [Использование строки для новых записей в элементе управления Windows Forms DataGridView](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления DataGridView](datagridview-control-overview-windows-forms.md)
- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
