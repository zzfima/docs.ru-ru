---
title: "Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "столбцы [Windows Forms], порядок"
  - "данные [Windows Forms], отображение"
  - "DataGridView - элемент управления [Windows Forms], порядок столбцов"
  - "Windows Forms, столбцы"
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
При выполнении привязки элемента управления Windows Forms <xref:System.Windows.Forms.DataGridView> к источнику данных порядок отображения автоматически создаваемых столбцов определяется источником данных.  Если вас не устраивает данный порядок отображения столбцов, его можно изменить с помощью конструктора.  Можно также добавить к элементу управления несвязанные столбцы и изменить порядок их отображения.  Дополнительные сведения об изменении порядка отображения столбцов программным путем см. в разделе [Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы изменить порядок отображения столбцов с использованием конструктора, выполните следующие действия:  
  
1.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView> и выберите **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  Нажимайте стрелку вверх или вниз справа от списка **Выбранные столбцы** до тех пор, пока выбранный столбец не окажется в нужной позиции.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)