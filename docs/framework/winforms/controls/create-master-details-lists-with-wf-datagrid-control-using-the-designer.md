---
title: "Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "DataGrid - элемент управления [Windows Forms], списки типа "основной-подробности""
  - "списки типа "основной-подробности""
  - "связанные таблицы, отображение данных в элементе управления DataGrid"
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если объект <xref:System.Data.DataSet> содержит набор связанных таблиц, для представления данных в формате основных сведений можно использовать два элемента управления <xref:System.Windows.Forms.DataGrid>.  В этом случае один элемент управления <xref:System.Windows.Forms.DataGrid> является основной сеткой, а второй — сеткой сведений.  При выборе записи в основном списке все связанные дочерние записи отображаются в списке сведений.  Например, если в объекте <xref:System.Data.DataSet> находятся таблица "Customers" и связанная таблица "Orders", таблицу "Customers" можно указать в качестве основной сетки, а таблицу "Orders" — в качестве сетки сведений.  При выборе заказчика в основной сетке все заказы, связанные с ним в таблице "Orders", отобразятся в сетке сведений.  
  
 Для следующей процедуры требуется проект **Приложение Windows**.  Сведения о настройке такого проекта см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать список основных сведений в конструкторе  
  
1.  Добавьте в форму два элемента управления <xref:System.Windows.Forms.DataGrid>.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится в **панели элементов**.  Дополнительные сведения см. в разделе [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ru-ru/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Следующие шаги нельзя использовать в [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], где для привязки данных при разработке используется окно **Источники данных**.  Дополнительные сведения см. в разделах [Привязка элементов управления к данным в Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md) и [Практическое руководство. Отображение связанных данные в приложении Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
2.  Перетащите несколько таблиц из **обозревателя серверов** в форму.  
  
3.  В меню**Данные** выберите **Создать набор данных**.  
  
4.  Задайте отношения между таблицами с помощью конструктора XML.  Дополнительные сведения см. в документе "How to: Create One\-to\-Many Relationships in XML Schemas and Datasets" в сети MSDN.  
  
5.  Сохраните отношения, выбрав в меню **Файл** команду **Сохранить все**.  
  
6.  Настройте элемент управления <xref:System.Windows.Forms.DataGrid>, который требуется назначить основной сеткой, следующим образом.  
  
    1.  Выберите <xref:System.Data.DataSet> в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A>.  
  
    2.  Выберите основную таблицу \(например, "Customers"\) в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A>.  
  
7.  Настройте элемент управления <xref:System.Windows.Forms.DataGrid>, который требуется назначить сеткой сведений, следующим образом.  
  
    1.  Выберите <xref:System.Data.DataSet> в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A>.  
  
    2.  Выберите связь \(например, "Customers.CustOrd"\) между основной таблицей и таблицей сведений в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGrid.DataMember%2A>.  Чтобы просмотреть связь, разверните узел, щелкнув знак плюс \(**\+**\) рядом с основной таблицей в раскрывающемся списке.  
  
## См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Привязка элементов управления к данным в Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)