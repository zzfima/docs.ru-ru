---
title: "Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора | Microsoft Docs"
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
  - "элементы управления с привязкой"
  - "элементы управления с привязкой, DataGrid - элемент управления"
  - "привязка данных, DataGrid - элемент управления"
  - "элементы управления с привязкой к данным, DataGrid"
  - "DataGrid - элемент управления [Windows Forms], привязка данных"
  - "наборы данных [Windows Forms], привязка данных к элементу управления DataGrid"
  - "элементы управления Windows Forms, привязка данных"
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.DataGrid> разработан специально для отображения сведений из источника данных.  Привязка элемента управления осуществляется путем задания свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> в режиме разработки или путем вызова метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> во время выполнения.  Несмотря на то что данные можно открывать из различных источников, обычно в качестве источников используются наборы данных и представления данных.  
  
 Если источник данных доступен в режиме разработки, например, в форме находится экземпляр набора данных или представление данных, сетку можно привязать к источнику данных на этом этапе.  Затем можно просмотреть, как данные отображаются в сетке.  
  
 Кроме того, сетку можно привязать программными средствами во время выполнения.  Это используется в тех случаях, когда требуется указать источник данных, основанный на сведениях, получаемых во время выполнения.  Например, в приложении может быть реализована возможность указания имени таблицы для просмотра.  Это также может потребоваться при отсутствии источника данных в режиме разработки.  Сюда относятся такие источники данных, как массивы, коллекции, нетипизированные наборы и устройства для считывания данных.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится в **панели элементов**.  Дополнительные сведения о его добавлении см. в разделе [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ru-ru/458e119e-17fe-450b-b889-e31c128bd7e0).  Кроме того, в [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] можно использовать окно **Источники данных** для привязки данных во время разработки.  Дополнительные сведения см. в разделе [Привязка элементов управления к данным в Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы выполнить привязку данных элемента управления DataGrid к одной таблице в конструкторе  
  
1.  Укажите в свойстве элемента управления <xref:System.Windows.Forms.DataGrid.DataSource%2A> объект, содержащий элементы данных для привязки.  
  
2.  Если источником данных является набор данных, укажите в свойстве <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя таблицы для привязки.  
  
3.  Если источником данных является набор данных или представление данных, основанное на таблице DataSet, добавьте код в форму для заполнения набора данных.  
  
     Текст программы зависит от расположения, из которого данные поступают в набор.  Если набор данных заполняется непосредственно из базы данных, обычно вызывается метод `Fill` адаптера данных, как в приведенном ниже примере, который заполняет набор данных с именем `DsCategories1`.  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  \(Необязательно\). Добавьте в сетку требуемые стили таблиц и столбцов.  
  
     Если стили таблиц отсутствуют, таблица отобразится с минимальным форматированием, при этом все столбцы будут доступны для просмотра.  
  
### Чтобы выполнить привязку данных элемента управления DataGrid к нескольким таблицам в конструкторе  
  
1.  Укажите в свойстве элемента управления <xref:System.Windows.Forms.DataGrid.DataSource%2A> объект, содержащий элементы данных для привязки.  
  
2.  Если в наборе данных имеются связанные таблицы \(т. е. имеется объект связи\), укажите в свойстве <xref:System.Windows.Forms.DataGrid.DataMember%2A> имя родительской таблицы.  
  
3.  Напишите код для заполнения набора данных.  
  
## См. также  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Доступ к данным в Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md)