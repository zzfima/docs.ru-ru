---
title: "Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "столбцы [Windows Forms], добавление данных к элементу управления DataGrid"
  - "DataGrid - элемент управления [Windows Forms], добавление таблиц и столбцов"
  - "таблицы [Windows Forms], добавление данных к элементу управления DataGrid"
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Данные в элементе управления Windows Forms <xref:System.Windows.Forms.DataGrid> можно отображать в таблицах и строках, создавая объекты <xref:System.Windows.Forms.DataGridTableStyle> и добавляя их в объект <xref:System.Windows.Forms.GridTableStylesCollection>, доступ к которому можно получить с помощью свойства <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления <xref:System.Windows.Forms.DataGrid>.  Каждый стиль таблицы позволяет отображать содержимое таблицы данных, указанной в свойстве <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> объекта <xref:System.Windows.Forms.DataGridTableStyle>.  При использовании стиля таблицы, в котором не определены стили столбцов, по умолчанию отображаются все столбцы таблицы данных.  Можно ограничить число отображаемых столбцов, добавив объекты <xref:System.Windows.Forms.DataGridColumnStyle> в объект <xref:System.Windows.Forms.GridColumnStylesCollection>, доступ к которому можно получить с помощью свойства <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> любого объекта <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Для следующих процедур требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGrid>.  Сведения о настройке такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] элемент управления <xref:System.Windows.Forms.DataGrid> по умолчанию не находится в **панели элементов**.  Дополнительные сведения о его добавлении см. в разделе [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ru-ru/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить таблицу в элемент управления DataGrid в конструкторе  
  
1.  Чтобы представить данные в таблице, необходимо сначала привязать элемент управления <xref:System.Windows.Forms.DataGrid> к набору данных.  Дополнительные сведения см. в разделе [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Выберите свойство <xref:System.Windows.Forms.DataGrid.TableStyles%2A> элемента управления <xref:System.Windows.Forms.DataGrid> в окне "Свойства" и нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством, чтобы открыть окно **Редактор коллекции DataGridTableStyle**.  
  
3.  В редакторе коллекции нажмите кнопку **Добавить** для добавления стиля таблицы.  
  
4.  Нажмите кнопку **ОК**, чтобы закрыть редактор коллекции, а затем снова отройте его, нажав кнопку с многоточием рядом со свойством <xref:System.Windows.Forms.DataGrid.TableStyles%2A>  
  
     В открывшемся редакторе коллекции все таблицы данных, связанные с элементом управления, отобразятся в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> стиля таблицы.  
  
5.  В поле **Члены** редактора коллекции выберите стиль таблицы.  
  
6.  В поле **Свойства** редактора коллекции выберите значение <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> для таблицы, которую требуется отобразить.  
  
### Чтобы добавить столбец в элемент управления DataGrid в конструкторе  
  
1.  В поле **Члены** окна **Редактор коллекции DataGridTableStyle** выберите требуемый стиль таблицы.  В поле **Свойства** редактора коллекции выберите коллекцию <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>, а затем нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством, чтобы открыть окно **Редактор коллекции DataGridColumnStyle**.  
  
2.  В редакторе коллекции нажмите кнопку **Добавить**, чтобы добавить стиль столбца, или нажмите кнопку со стрелкой вниз рядом с кнопкой **Добавить**, чтобы выбрать тип столбца.  
  
     В раскрывающемся списке можно выбрать один из двух типов: либо <xref:System.Windows.Forms.DataGridTextBoxColumn>, либо <xref:System.Windows.Forms.DataGridBoolColumn>.  
  
3.  Нажмите кнопку OK, чтобы закрыть окно **Редактор коллекции DataGridColumnStyle**, а затем снова отройте его, нажав кнопку с многоточием рядом со свойством <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.  
  
     В открывшемся редакторе коллекции все столбцы данных в связанной таблице данных отобразятся в раскрывающемся списке свойства <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> стиля столбца.  
  
4.  В поле **Члены** редактора коллекции выберите стиль столбца.  
  
5.  В поле **Свойства** редактора коллекции выберите значение <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> для столбца, который требуется отобразить.  
  
## См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)