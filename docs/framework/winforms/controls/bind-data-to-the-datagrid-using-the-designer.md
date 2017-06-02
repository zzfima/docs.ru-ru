---
title: "Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "источники данных, привязка к элементам управления Windows Forms"
  - "DataGridView - элемент управления [Windows Forms], привязка данных"
  - "элементы управления Windows Forms, привязка к источнику данных"
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора
Конструктор можно использовать для соединения элемента управления <xref:System.Windows.Forms.DataGridView> с источниками данных разных видов, включая базы данных, бизнес\-объекты и веб\-службы.  При связывании элемента управления с источником данных с помощью конструктора элемент управления автоматически привязывается к компоненту <xref:System.Windows.Forms.BindingSource>, представляющему источник данных.  Кроме того, в элементе управления автоматически генерируются столбцы в соответствии с информацией о схеме, предоставленной источником данных.  
  
 После генерирования столбцов их можно изменить в соответствии с собственными потребностями.  Например, можно удалить или спрятать столбцы, которые не должны отображаться, можно изменить порядок столбцов или изменить их типы.  Дополнительные сведения об изменении столбцов приведены в темах, перечисленных в разделе "См. также".  
  
 Можно также привязать несколько элементов управления <xref:System.Windows.Forms.DataGridView> к связанным таблицам для создания отношений "основной\/подробности".  В этой конфигурации один элемент управления отображает родительскую таблицу, а другой — только те строки дочерней таблицы, которые имеют отношение к текущей строке родительской таблицы.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение связанных данные в приложении Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView> или два таких элемента для отношения "основной\/подробности".  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Для привязки элемента управления к источнику данных выполните следующие действия  
  
1.  Щелкните значок смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
2.  Щелкните стрелку раскрывающегося списка, чтобы выбрать параметр **Выбор источника данных**.  
  
3.  Если проект еще не имеет источника данных, выберите пункт **Добавить источник данных проекта** и следуйте указаниям мастера.  
  
     Дополнительные сведения см. в разделе [мастер настройки источника данных](../Topic/Data%20Source%20Configuration%20Wizard.md).  Новый источник данных появится в выпадающем окне **Выбор источника данных**.  Если новый источник данных содержит только один элемент, например одну таблицу базы данных, то элемент управления автоматически будет привязан к этому источнику.  В противном случае перейдите к следующему этапу.  
  
4.  Разверните узлы **Другие источники данных** и **Источники данных проекта**, если они еще не развернуты, и выберите источник данных для привязки к нему элемента управления.  
  
5.  Если источник данных содержит более одного члена, например в случае создания источника <xref:System.Data.DataSet?displayProperty=fullName>, содержащего несколько таблиц, разверните соответствующий источник данных и выберите нужный член для привязки к нему элемента управления.  
  
6.  Для создания отношений "основной\/подробности" в выпадающем окне **Выбор источника данных** для второго элемента управления <xref:System.Windows.Forms.DataGridView> разверните источник <xref:System.Windows.Forms.BindingSource>, созданный для родительской таблицы, а затем выберите соответствующую дочернюю таблицу из отображенного списка.  
  
    > [!NOTE]
    >  Если проект уже имеет источник данных, то для создания формы данных можно использовать окно **Источники данных**.  Дополнительные сведения см. в разделе [окно "Источники данных"](../Topic/Data%20Sources%20Window.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 [Практическое руководство. Подключение к данным в базе данных](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)   
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)   
 [Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [окно "Источники данных"](../Topic/Data%20Sources%20Window.md)   
 [Практическое руководство. Отображение связанных данные в приложении Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)