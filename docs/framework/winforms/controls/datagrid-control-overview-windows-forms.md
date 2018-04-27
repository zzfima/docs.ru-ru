---
title: Общие сведения об элементе управления DataGrid (Windows Forms)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataGrid
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- columns [Windows Forms], DataGrid control
- data sources [Windows Forms], binding to DataGrid control
- tables [Windows Forms], binding to DataGrid control
- DataGrid control [Windows Forms], data binding
- DataGrid control [Windows Forms], about DataGrid control
- parent tables in DataGrid control
- tables [Windows Forms], displaying in DataGrid control
- data grids [Windows Forms], about data grids
- multiple tables in DataGrid control
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- parent table navigation in DataGrid
- child tables [Windows Forms], dataGrid control
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd74ed0e31fff211f0197ad27f297f9fbecf5cab
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="datagrid-control-overview-windows-forms"></a>Общие сведения об элементе управления DataGrid (Windows Forms)
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> в Windows Forms отображает данные в виде ряда строк и столбцов. В самом простом случае сетка привязана к источнику данных с помощью единственной таблицы, не содержащей связей. В этом случае данные отображаются в виде простых строк и столбцов, как в электронной таблице. Дополнительные сведения о привязке данных к другим элементам управления см. в разделе [Привязка данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
 Если элемент <xref:System.Windows.Forms.DataGrid> привязан к данным с помощью нескольких связанных таблиц и в сетке включена навигация, в каждой строке сетки будут отображаться расширители. С помощью расширителя пользователь может переходить из родительской таблицы в дочернюю. При щелчке узла отображается дочерняя таблица, а при нажатии кнопки "Назад" — исходная родительская таблица. Таким образом в сетке отображаются иерархические связи между таблицами.  
  
 На следующем снимке экрана показан элемент управления DataGrid, привязанный к данным с помощью нескольких таблиц.  
  
 ![Элемент управления DataGrid привязан к данным с помощью нескольких таблиц](../../../../docs/framework/winforms/controls/media/vbcontrol1.gif "vbControl1")  
Элемент управления DataGrid, привязанный к данным с помощью нескольких таблиц  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> может предоставлять пользовательский интерфейс для набора данных, навигацию между связанными таблицами и широкие возможности форматирования и редактирования.  
  
 Отображение и обработка данных — это разные функции: элемент управления обрабатывает пользовательский интерфейс, тогда как как обновление данных обрабатывается архитектурой привязки данных Windows Forms и поставщиками данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Таким образом обеспечивается синхронизация элементов управления, привязанных к одному источнику данных.  
  
> [!NOTE]
>  Если вы знакомы с элементом управления DataGrid в Visual Basic 6.0, вы можете обратить внимание на значительные отличия элемента управления <xref:System.Windows.Forms.DataGrid> в Windows Forms.  
  
 Если сетка привязана к <xref:System.Data.DataSet>, столбцы и строки автоматически создаются, форматируются и заполняются. Дополнительные сведения см. в разделе [Привязка данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md). После создания элемента управления <xref:System.Windows.Forms.DataGrid> можно добавлять, удалять, изменять порядок и форматировать столбцы и строки в зависимости от потребностей.  
  
## <a name="binding-data-to-the-control"></a>Привязка данных к элементу управления  
 Для работы элемента управления <xref:System.Windows.Forms.DataGrid> он должен быть привязан к источнику данных с помощью свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> во время разработки или метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> во время выполнения. Эта привязка указывает <xref:System.Windows.Forms.DataGrid> на созданный экземпляр объекта источника данных, например <xref:System.Data.DataSet> или <xref:System.Data.DataTable>. Элемент управления <xref:System.Windows.Forms.DataGrid> отображает результаты действий, выполняемых с данными. Большинство операций с данными выполняются не через <xref:System.Windows.Forms.DataGrid>, а через источник данных.  
  
 Если данные в привязанном наборе данных обновляются посредством какого-либо механизма, элемент управления <xref:System.Windows.Forms.DataGrid> отражает изменения. Если сетка данных и его стили таблиц и столбцов имеют `ReadOnly` свойство `false`, в наборе данных можно обновлять с помощью <xref:System.Windows.Forms.DataGrid> элемента управления.  
  
 В элементе управления <xref:System.Windows.Forms.DataGrid> на определенный момент времени может отображаться только одна таблица. Если между таблицами определено отношение "родительская-дочерняя", пользователь может перемещаться между связанными таблицами для выбора таблицы, которая будет отображаться в элементе управления <xref:System.Windows.Forms.DataGrid>. Сведения о привязке <xref:System.Windows.Forms.DataGrid> управления [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] источника данных во время разработки или во время выполнения, в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
 Источники данных, допустимые для <xref:System.Windows.Forms.DataGrid>, включают следующие:  
  
-   Класс <xref:System.Data.DataTable>  
  
-   Класс <xref:System.Data.DataView>  
  
-   Класс <xref:System.Data.DataSet>  
  
-   Класс <xref:System.Data.DataViewManager>  
  
 Если источником является набор данных, он может быть объектом в форме или объектом, переданным в форму веб-службой XML. Привязку можно выполнять к типизированным или нетипизированным наборам данных.  
  
 Кроме того, элемент управления <xref:System.Windows.Forms.DataGrid> можно привязать к дополнительным структурам, если объекты в структуре (например, элементы в массиве) предоставляют открытые свойства. В сетке будут отображаться все открытые свойства элементов в структуре. Например, если выполняется привязка элемента управления <xref:System.Windows.Forms.DataGrid> к массиву объектов клиента, все открытые свойства этих объектов отобразятся в сетке. Иногда это означает, что хотя вы можете выполнить привязку к структуре, полученная связанная структура не всегда будет иметь практическое применение. Например, можно выполнить привязку к массиву целых чисел, но поскольку тип данных `Integer` не поддерживает открытое свойство, данные в сетке отображаться не будут.  
  
 Можно выполнить привязку к следующим структурам, если их элементы предоставляют открытые свойства:  
  
-   к любым компонентам, реализующим интерфейс <xref:System.Collections.IList> (сюда входят одномерные массивы);  
  
-   к любым компонентам, реализующим интерфейс <xref:System.ComponentModel.IListSource>;  
  
-   к любым компонентам, реализующим интерфейс <xref:System.ComponentModel.IBindingList>.  
  
 Дополнительные сведения о возможных источниках данных см. в разделе [Источники данных, поддерживаемые Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
## <a name="grid-display"></a>Отображение сетки  
 Обычно элемент управления <xref:System.Windows.Forms.DataGrid> используется для отображения одной таблицы данных из набора данных. Однако этот элемент управления можно также использовать для отображения нескольких таблиц, включая связанные таблицы. Отображение сетки настраивается автоматически в зависимости от источника данных. В таблице ниже указано, что именно отображается в сетке в разных конфигурациях.  
  
|Содержимое набора данных|Что отображается|  
|--------------------------|-----------------------|  
|Одна таблица|Таблица отображается в сетке.|  
|Несколько таблиц|В сетке может отображаться иерархическое представление, с помощью которого пользователь может переходить к нужной таблице.|  
|Несколько связанных таблиц|В сетке может отображаться иерархическое представление, с помощью которого можно выбирать таблицы. Кроме того, можно задать отображение в сетке родительской таблицы. Записи в родительской таблице позволяют пользователям переходить к связанным строкам дочерних таблиц.|  
  
> [!NOTE]
>  Таблицы в наборе данных связываются с помощью <xref:System.Data.DataRelation>.  См. также [гиперссылка «http://msdn.microsoft.com/library/dbwcse3d(v=vs.110)"отношения в наборах данных](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.110\)) или [отношения в наборах данных](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.120\)).  
  
 Когда элемент управления <xref:System.Windows.Forms.DataGrid> отображает таблицу и свойству <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> присвоено значение `true`, данные можно сортировать, щелкая заголовки столбцов. Пользователь также может добавлять строки и редактировать ячейки.  
  
 Связи между наборами таблиц отображаются для пользователей с помощью структуры навигации "родительская-дочерняя". Родительские таблицы представляют высший уровень данных, а дочерние таблицы — это таблицы данных, производные от отдельных листингов в родительских таблицах. В каждой родительской строке, содержащей дочернюю таблицу, отображаются расширители. При щелчке расширителя создается список гиперссылок на дочерние таблицы. Когда пользователь переходит по ссылке, отображается дочерняя таблица. При щелчке значка "показать/скрыть" для родительских строк (![значок "показать/скрыть" для родительских строк](../../../../docs/framework/winforms/controls/media/vbicon.gif "vbIcon")) сведения о родительской таблице будут скрываться или вновь выводиться на экран, если пользователь скрыл их ранее. Пользователь может нажать кнопку "Назад", чтобы вернуться к предыдущей таблице.  
  
## <a name="columns-and-rows"></a>Столбцы и строки  
 <xref:System.Windows.Forms.DataGrid> состоит из коллекции объектов <xref:System.Windows.Forms.DataGridTableStyle>, содержащихся в свойстве <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления <xref:System.Windows.Forms.DataGrid>. Стиль таблицы может содержать коллекцию объектов <xref:System.Windows.Forms.DataGridColumnStyle>, содержащихся в свойстве <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> класса <xref:System.Windows.Forms.DataGridTableStyle>. Можно изменить <xref:System.Windows.Forms.DataGrid.TableStyles%2A> и <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойств с помощью редакторов коллекций, доступных через **свойства** окна.  
  
 К любому классу <xref:System.Windows.Forms.DataGridTableStyle>, связанному с элементом управления <xref:System.Windows.Forms.DataGrid>, можно получить доступ через коллекцию <xref:System.Windows.Forms.GridTableStylesCollection>. Коллекцию <xref:System.Windows.Forms.GridTableStylesCollection> можно изменить в конструкторе с помощью редактора коллекции <xref:System.Windows.Forms.DataGridTableStyle> или программным путем с помощью свойства <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления <xref:System.Windows.Forms.DataGrid>.  
  
 ![Объекты, включенные в элемент управления DataGrid](../../../../docs/framework/winforms/controls/media/vbcolumns1.gif "vbColumns1")  
На рисунке показаны объекты, включенные в элемент управления DataGrid.  
  
 Стили таблиц и столбцов синхронизируются с объектами <xref:System.Data.DataTable> и <xref:System.Data.DataColumn> путем задания для их свойства `MappingName` соответствующих свойств <xref:System.Data.DataTable.TableName%2A> и <xref:System.Data.DataColumn.ColumnName%2A>. Когда класс <xref:System.Windows.Forms.DataGridTableStyle>, не имеющий стилей столбцов, добавляется в элемент управления <xref:System.Windows.Forms.DataGrid>, привязанный к допустимому источнику данных, и для свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> этого стиля таблицы задается допустимое свойство <xref:System.Data.DataTable.TableName%2A>, для этого стиля таблицы создается коллекция объектов <xref:System.Windows.Forms.DataGridColumnStyle>. Для каждого объекта <xref:System.Data.DataColumn> в коллекции <xref:System.Data.DataTable.Columns%2A> объекта <xref:System.Data.DataTable> в коллекцию <xref:System.Windows.Forms.GridColumnStylesCollection> добавляется соответствующий класс <xref:System.Windows.Forms.DataGridColumnStyle>. Доступ к коллекции <xref:System.Windows.Forms.GridColumnStylesCollection> осуществляется через свойство <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> класса <xref:System.Windows.Forms.DataGridTableStyle>. Столбцы можно добавлять или удалять из сетки, используя метод <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> или <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> для коллекции <xref:System.Windows.Forms.GridColumnStylesCollection>. Дополнительные сведения см. в разделе [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) и [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md).  
  
 Коллекция типов столбцов расширяет класс <xref:System.Windows.Forms.DataGridColumnStyle>, добавляя целый ряд возможностей форматирования и редактирования. Все типы столбцов наследуют от базового класса <xref:System.Windows.Forms.DataGridColumnStyle>. Создаваемый класс зависит от свойства <xref:System.Data.DataColumn.DataType%2A> класса <xref:System.Data.DataColumn>, который является базовым для <xref:System.Web.UI.WebControls.DataGridColumn>. Например, объект <xref:System.Data.DataColumn>, для свойства <xref:System.Data.DataColumn.DataType%2A> которого задано значение <xref:System.Boolean>, будет связан с <xref:System.Windows.Forms.DataGridBoolColumn>. В следующей таблице описан каждый из этих типов столбцов.  
  
|Тип столбца|Описание|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|Принимает и отображает данные в виде форматированных или неформатированных строк. Возможности редактирования аналогичны возможностям редактирования данных в простом элементе <xref:System.Windows.Forms.TextBox>. Наследует от <xref:System.Windows.Forms.DataGridColumnStyle>.|  
|<xref:System.Windows.Forms.DataGridBoolColumn>|Принимает и отображает значения `true`, `false` и NULL. Наследует от <xref:System.Windows.Forms.DataGridColumnStyle>.|  
  
 Двойной щелчок правого края столбца изменяет размер столбца для отображения полной подписи и самой широкой записи.  
  
## <a name="table-styles-and-column-styles"></a>Стили таблиц и столбцов  
 После установки формата по умолчанию для элемента управления <xref:System.Windows.Forms.DataGrid> можно настроить цвета, которые будут использоваться при отображении определенных таблиц в сетке данных.  
  
 Для этого необходимо создать экземпляры класса <xref:System.Windows.Forms.DataGridTableStyle>. Стили таблиц определяют форматирование отдельных таблиц, которое не следует путать с форматированием самого элемента управления <xref:System.Windows.Forms.DataGrid> по умолчанию. В определенный момент времени каждая таблица может иметь только один заданный для нее стиль.  
  
 В некоторых случаях требуется, чтобы определенный столбец отличался от остальных столбцов таблицы данных. Можно создать настраиваемый набор стилей столбцов с помощью свойства <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.  
  
 Стили столбцов связаны со столбцами в наборе данных так же, как стили таблиц связаны с таблицами данных. Так же как и таблица может иметь только один стиль на конкретный момент времени, каждому столбцу можно назначить только один стиль в рамках определенного стиля таблицы. Эта связь определяется в свойстве <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> столбца.  
  
 Если созданный стиль таблицы без добавления в него стили столбцов Visual Studio добавляет стили столбцов по умолчанию при создании формы и сетки во время выполнения. Тем не менее если созданный стиль таблицы и добавить в него стили столбцов, Visual Studio не создает стили столбцов. Кроме того, необходимо определить стили столбцов и назначить их с помощью имени сопоставления, чтобы нужные столбцы отображались в сетке.  
  
 Поскольку выбор столбцов для отображения в сетке данных выполняется путем назначения им стиля столбца, можно включить в набор данных столбцы данных, которые не отображаются в сетке, не назначая им стиль. При этом, поскольку столбец данных включен в набор данных, можно программным образом редактировать данные, которые не отображаются.  
  
> [!NOTE]
>  Как правило, создание стилей столбцов и добавление их в коллекцию стилей столбцов выполняется перед добавлением стилей таблиц в коллекцию стилей таблиц. При добавлении в коллекцию пустого стиля таблицы стили столбцов создаются автоматически. Следовательно, при попытке добавить в коллекцию новые стили столбцов с повторяющимися значениями <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> будет создано исключение.  
>   
>  Иногда может потребоваться изменить один столбец из нескольких (например, набор данных содержит 50 столбцов, а вам нужны только 49 из них). В этом случае проще импортировать все 50 столбцов и программно удалить один, а не добавлять все 49 столбцов по отдельности.  
  
## <a name="formatting"></a>Форматирование  
 Форматирование, которое может применяться к элементу управления <xref:System.Windows.Forms.DataGrid>, включает стили границ, стили линий сетки, шрифты, свойства подписи, выравнивание данных и чередующиеся фоновые цвета для строк. Дополнительные сведения см. в разделе [Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md).  
  
## <a name="events"></a>События  
 Помимо общих событий управления, таких как <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter> и <xref:System.Windows.Forms.DataGrid.Scroll>, элемент управления <xref:System.Windows.Forms.DataGrid> поддерживает события, связанные с редактированием и навигацией в сетке. Свойство <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> определяет, какая ячейка выбрана. Событие <xref:System.Windows.Forms.DataGrid.CurrentCellChanged> вызывается, когда пользователь переходит к новой ячейке. При переходе к новой таблице через отношение "родительская-дочерняя" вызывается событие <xref:System.Windows.Forms.DataGrid.Navigate>. Событие <xref:System.Windows.Forms.DataGrid.BackButtonClick> возникает, когда пользователь нажимает кнопку "Назад" при просмотре дочерней таблицы, а событие <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick> возникает при нажатии значка "показать/скрыть" для родительских строк.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)
