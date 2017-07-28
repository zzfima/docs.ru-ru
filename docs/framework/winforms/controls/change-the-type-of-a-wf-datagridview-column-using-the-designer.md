---
title: "Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "столбцы [Windows Forms], типы"
  - "данные [Windows Forms], отображение"
  - "DataGridView - элемент управления [Windows Forms], изменение типа столбца"
  - "Windows Forms, столбцы"
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
Иногда требуется изменить тип столбца, который уже был добавлен в элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView>.  Например, необходимо изменить типы некоторых столбцов, которые были автоматически созданы при привязке элемента управления к источнику данных.  Это полезно в том случае, когда в столбцах отображаемой таблицы содержатся внешние ключи для ссылки на строки связанной таблицы.  В этом случае может потребоваться заменить столбцы с текстовыми полями, в которых отображаются эти внешние ключи, столбцами типа "поле со списком", в которых отображаются более понятные значения из связанной таблицы.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы изменить тип столбца с использованием конструктора, выполните следующие действия:  
  
1.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView> и выберите **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  В сетке **Свойства столбца** установите для свойства `ColumnType` новый тип столбца.  
  
    > [!NOTE]
    >  Свойство `ColumnType` определяет класс, соответствующий типу столбца, и может использоваться только в процессе разработки.  Это не фактическое свойство, определенное в классе столбца.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)