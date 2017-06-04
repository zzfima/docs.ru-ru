---
title: "Архитектура элементов управления DataGridView (Windows Forms) | Microsoft Docs"
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
  - "DataGridView - элемент управления [Windows Forms], архитектура"
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Архитектура элементов управления DataGridView (Windows Forms)
Элемент управления <xref:System.Windows.Forms.DataGridView> и и все связанные с ним классы должны стать гибкой, расширяемой системой для отображения и правки табличных данных.  Все эти классы содержатся в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName> и имеют префикс "DataGridView" в имени.  
  
## Элементы архитектуры  
 Основные сопутсвующие классы <xref:System.Windows.Forms.DataGridView> являются производными <xref:System.Windows.Forms.DataGridViewElement>.  В следующей объектной модели показана иерархия наследования <xref:System.Windows.Forms.DataGridViewElement>.  
  
 ![Объектная модель DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.png "DataGridViewElement")  
Объектная модель DataGridViewElement  
  
 Класс <xref:System.Windows.Forms.DataGridViewElement> предоставляет ссылку на родительский элемент управления <xref:System.Windows.Forms.DataGridView> и имеет свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A> со значением, представляющим набор значений из перечисления <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
 В следующих разделах сопутствующие классы <xref:System.Windows.Forms.DataGridView> описаны более подробно.  
  
### DataGridViewElementStates  
 Перечисление <xref:System.Windows.Forms.DataGridViewElementStates> содержит следующие значения:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
 Значения этого перечисления можно объединить с поразрядными логическими операторами так, чтобы свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A> могло выражать более одного состояния одновременно.  Например, <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates>, <xref:System.Windows.Forms.DataGridViewElementStates> и <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
### Ячейки и зоны  
 Элемент управления <xref:System.Windows.Forms.DataGridView> состоит из двух основных типов объектов – ячеек и зон.  Все ячейки являются производными от базового класса <xref:System.Windows.Forms.DataGridViewCell>.  Два типа зон – <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow> – являются производными от базового класса <xref:System.Windows.Forms.DataGridViewBand>.  
  
 Элемент управления <xref:System.Windows.Forms.DataGridView> взаимодействует с несколькими классами, но чаще всего встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>.  
  
### DataGridViewCell  
 Основной единицей взаимодействия для <xref:System.Windows.Forms.DataGridView> является ячейка.  Ячейки располагаются в центре и, как правило, используются для ввода данных.  Для обращения к ячейкам можно использовать коллекцию <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> класса <xref:System.Windows.Forms.DataGridViewRow>, а для обращения к выбранным ячейкам – коллекцию <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> класса <xref:System.Windows.Forms.DataGridView>.  В следующей объектной модели показан пример использования и иерархия наследования <xref:System.Windows.Forms.DataGridViewCell>.  
  
 ![Объектная модель DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.png "DataGridViewCell")  
Объектная модель DataGridViewCell  
  
 Тип <xref:System.Windows.Forms.DataGridViewCell> является абстрактным базовым классом, от которого наследуют все типы ячеек.  <xref:System.Windows.Forms.DataGridViewCell> и его производные типы не являются элементами управления Windows Forms, но в некоторых из них размещаются элементы управления Windows Forms.  Любая возможность изменения, поддерживаемая ячейкой, как правило обрабатывается элементом управления ведущего приложения.  
  
 Объекты <xref:System.Windows.Forms.DataGridViewCell> не управляют собственным внешним видом и оформлением так, как это делают элементы управления Windows Forms.  Вместо этого, <xref:System.Windows.Forms.DataGridView> отвечает за внешний вид собственных объектов <xref:System.Windows.Forms.DataGridViewCell>.  Внешний вид и поведение ячеек можно в значительной степени изменять путем взаимодействия со свойствами и событиями элемента управления <xref:System.Windows.Forms.DataGridView>.  В случае особых требований к настройкам, выходящим за пределы возможностей элемента управления <xref:System.Windows.Forms.DataGridView>, можно реализовать собственный производный от <xref:System.Windows.Forms.DataGridViewCell> класс или один из его дочерних классов.  
  
 В следующем списке перечислены производные от <xref:System.Windows.Forms.DataGridViewCell> классы.  
  
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
  
### DataGridViewColumn  
 Схема вложененного хранилища данных элемента управления <xref:System.Windows.Forms.DataGridView> выражена в столбцах элемента управления <xref:System.Windows.Forms.DataGridView>.  Доступ к столбцам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить при помощи коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>.  Доступ к выбранным столбцам можно получить при помощи коллекции <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  В следующей объектной модели показан пример использования и иерархия наследования <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 ![Объектная модель DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.png "DataGridViewColumn")  
Объектная модель DataGridViewColumn  
  
 Некоторым ключевым типам ячеек соответствуют типы столбцов.  Они являются производными базового класса <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 В следующем списке перечислены унаследованные от <xref:System.Windows.Forms.DataGridViewColumn> классы.  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Пользовательские типы столбцов  
  
### Элементы управления для редактирования DataGridView  
 Ячейки, поддерживающие расширенные функции редактирования, как правило, используют элемент управления ведущего приложения, являющийся производным от элемента управления Windows Forms.  Эти элементы управления реализуют интерфейс <xref:System.Windows.Forms.IDataGridViewEditingControl>.  В следующей объектной модели показано использование этих элементов управления.  
  
 ![Объектная модель элемента управления для редактирования DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.png "DataGridViewEditing")  
Объектная модель элемента управления для редактирования DataGridView  
  
 Следующие элементы управления для редактирования предоставляются с элементом управления <xref:System.Windows.Forms.DataGridView>:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Дополнительные сведения о создании собственных элементов управления для редактирования см. в разделе [Практическое руководство. Размещение элементов управления в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 В следующей таблице показана связь между типами ячеек, типами столбцов и элементами управления для редактирования.  
  
|Тип ячейки|Элемент управления ведущего приложения|Тип столбца|  
|----------------|--------------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|нет|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|нет|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|нет|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|нет|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### DataGridViewRow  
 Класс <xref:System.Windows.Forms.DataGridViewRow> отображает поля данных записи из хранилища данных, в который вложен элемент управления <xref:System.Windows.Forms.DataGridView>.  Доступ к строкам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить при помощи коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>.  Доступ к выбранным строкам можно получить при помощи коллекции <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.  В следующей объектной модели показан пример использования и иерархия наследования <xref:System.Windows.Forms.DataGridViewRow>.  
  
 ![Объектная модель DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.png "DataGridViewRow")  
Объектная модель DataGridViewRow  
  
 Собственные типы можно получить из класса <xref:System.Windows.Forms.DataGridViewRow>, однако в большинстве случаев это не потребуется.  Элемент управления <xref:System.Windows.Forms.DataGridView> имеет несколько связанных со строками событий и свойств для настройки поведения его объектов <xref:System.Windows.Forms.DataGridViewRow>.  
  
 После включения свойства <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> элемента управления <xref:System.Windows.Forms.DataGridView>, в качестве последней появляется специальная строка для добавления новых строк.  Эта строка является частью коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>, но обладает особыми функциональными возможностями, требующими внимания.  Дополнительные сведения см. в разделе [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## См. также  
 [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)