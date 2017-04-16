---
title: "Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "ячейки, настройки в элементе управления DataGridView"
  - "столбцы [Windows Forms], настройки в элементе управления DataGridView"
  - "DataGridView - элемент управления [Windows Forms], настройка ячеек"
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms
Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить несколькими способами с помощью свойств, событий и классов\-компаньонов.  В ряде случаев к ячейкам могут предъявляться требования, когда этих функций будет недостаточно.  Вы можете создать пользовательский класс <xref:System.Windows.Forms.DataGridViewCell> для расширения функциональных возможностей.  
  
 Пользовательский класс <xref:System.Windows.Forms.DataGridViewCell> создается как производный от базового класса <xref:System.Windows.Forms.DataGridViewCell> или одного из его производных классов.  Хотя любой тип ячейки можно отобразить в любом типе столбца, как правило, потребуется также создать пользовательский класс <xref:System.Windows.Forms.DataGridViewColumn>, специально предназначенный для отображения пользовательского типа ячейки.  Классы столбцов являются производными от <xref:System.Windows.Forms.DataGridViewColumn> или от одного из его производных типов.  
  
 В примере кода ниже создается пользовательский класс ячейки с именем `DataGridViewRolloverCell`, который обнаруживает, когда указатель мыши пересекает границы ячейки.  Когда указатель мыши находится внутри границ ячейки, рисуется внутренняя рамка.  Этот новый тип является производным от <xref:System.Windows.Forms.DataGridViewTextBoxCell> и во всем остальном ведет себя так же, как и базовый класс.  Класс\-компаньон столбца имеет имя `DataGridViewRolloverColumn`.  
  
 Для использования этих классов необходимо создать форму, содержащую элемент управления <xref:System.Windows.Forms.DataGridView>, добавить один или несколько объектов `DataGridViewRolloverColumn` в коллекцию <xref:System.Windows.Forms.DataGridView.Columns%2A> и заполнить элемент управления строками со значениями.  
  
> [!NOTE]
>  Пример не будет работать правильно с пустыми строками.  Пустые строки создаются, например, при добавлении строк в элемент управления путем задания свойства <xref:System.Windows.Forms.DataGridView.RowCount%2A>.  Это происходит потому, что добавленные в этом случае строки автоматически становятся общими. Это означает, что экземпляры объектов `DataGridViewRolloverCell` не будут создаваться до тех пор, пока не будут нажаты отдельные ячейки, что отменяет блокирование связанных общих строк.  
  
 Так как подобная настройка ячеек требует, чтобы строки не были общими, она не подходит для использования с большими наборами данных.  Подробнее о совместном использовании строк см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
> [!NOTE]
>  При наследовании от класса <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewColumn> и добавлении в производный класс новых свойств необходимо переопределить метод `Clone`, чтобы копировать новые свойства в ходе операций копирования.  Кроме того, необходимо вызвать метод `Clone` базового класса, чтобы свойства базового класса копировались в новую ячейку или столбец.  
  
### Настройка ячеек и столбцов в элементе управления DataGridView  
  
1.  Создайте класс ячейки с именем `DataGridViewRolloverCell`, производный от типа <xref:System.Windows.Forms.DataGridViewTextBoxCell>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  Переопределите метод <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> в классе `DataGridViewRolloverCell`.  При переопределении сначала вызовите реализацию базового класса, которая отвечает за функциональные возможности размещенного текстового поля.  Затем с помощью метода <xref:System.Windows.Forms.Control.PointToClient%2A> элемента управления преобразуйте положение курсора \(в экранных координатах\) в координаты клиентской области <xref:System.Windows.Forms.DataGridView>.  Если координаты курсора попадают в границы ячейки, то рисуется внутренняя рамка.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  Переопределите методы <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> и <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> класса `DataGridViewRolloverCell`, чтобы ячейки отрисовывались повторно, когда указатель мыши пересекает их границы.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  Создайте класс с именем `DataGridViewRolloverCellColumn`, производный от типа <xref:System.Windows.Forms.DataGridViewColumn>.  В конструкторе назначьте новый объект `DataGridViewRolloverCell` его свойству <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## Пример  
 Полный пример кода включает небольшую тестовую форму, демонстрирующую поведение ячейки пользовательского типа.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Windows.Forms и System.Drawing.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)