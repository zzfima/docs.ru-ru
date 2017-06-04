---
title: "Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.DataGridViewAddColumnDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView - элемент управления [Windows Forms], добавление столбцов"
  - "DataGridView - элемент управления [Windows Forms], удаление столбцов"
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
Для отображения данных элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> должен содержать столбцы.  Если планируется ручное заполнение элемента управления, пользователь должен самостоятельно добавить столбцы.  Кроме того, можно выполнить привязку элемента управления к источнику данных для автоматического формирования и заполнения столбцов.  Если источник данных содержит больше столбцов, чем необходимо отобразить, можно удалить ненужные столбцы.  
  
 Для следующих процедур требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Добавление столбца с использованием конструктора  
  
1.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView> и выберите **Добавить столбец**.  
  
2.  В диалоговом окне **Добавление столбца** выберите параметр **Столбец привязки к данным**и выберите столбец из источника данных. Можно также выбрать параметр **Несвязанный столбец** и определить столбец, используя имеющиеся поля.  
  
3.  Если имеющиеся столбцы не заполнили уже область отображения элемента управления, нажмите кнопку **Добавить** для добавления столбца, который затем появится в конструкторе.  
  
    > [!NOTE]
    >  Свойства столбца можно изменить в диалоговом окне **Правка столбцов**, которое можно открыть из смарт\-тега элемента управления.  
  
### Удаление столбца с использованием конструктора  
  
1.  В смарт\-теге элемента управления выберите **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  Чтобы удалить столбец, нажмите кнопку **Удалить**, после чего он исчезнет из конструктора.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)