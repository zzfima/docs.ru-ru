---
title: "Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "столбцы [Windows Forms], только для чтения"
  - "данные [Windows Forms], отображение"
  - "DataGridView - элемент управления [Windows Forms], столбцы только для чтения"
  - "Windows Forms, столбцы"
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора
По умолчанию пользователи могут изменять текст и численные данные, отображаемые в элементе управления <xref:System.Windows.Forms.DataGridView> Windows Forms.  Чтобы отображать данные, не предназначенные для редактирования, необходимо сделать столбцы, содержащие данные, доступными только для чтения.  Сведения о том, как весь элемент управления сделать доступным только для чтения, см. в разделе [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы сделать столбец доступным только для чтения, используя конструктор  
  
1.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView> и выберите **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  В сетке **Свойства столбца** установите для свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> значение `true`.  
  
    > [!NOTE]
    >  Сделать столбец доступным только для чтения можно также при его добавлении, установив флажок **Только для чтения** в диалоговом окне **Добавление столбца**.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)