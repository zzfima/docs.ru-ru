---
title: "Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "столбцы [Windows Forms], фиксация"
  - "данные [Windows Forms], отображение"
  - "DataGridView - элемент управления [Windows Forms], фиксация столбцов"
  - "Windows Forms, столбцы"
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
При просмотре пользователями данных, отображаемых в элементе управления <xref:System.Windows.Forms.DataGridView> Windows Forms, у них иногда возникает необходимость частого обращения к одному столбцу или набору столбцов.  Например, при отображении таблицы сведений о пользователе, содержащей большое число столбцов, весьма удобно всегда отображать имя пользователя при прокручивании остальных столбцов за пределы видимой области.  
  
 Для этого необходимо выполнить замораживание столбцов в элементе управления.  При замораживании столбца все столбцы слева от него \(или справа для языков с письмом справа налево\) также замораживаются.  Замороженные столбцы остаются на месте в то время, как остальные столбцы можно прокручивать.  Если разрешено переупорядочивание столбцов, замороженные столбцы рассматриваются как группа, отличная от группы незамороженных столбцов.  Пользователи могут переставлять местами столбцы в каждой из групп, но не могут перемещать столбцы из одной группы в другую.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы заморозить столбец с использованием конструктора, выполните следующие действия:  
  
1.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView> и выберите **Правка столбцов**.  
  
2.  Выберите столбец из списка **Выбранные столбцы**.  
  
3.  В сетке **Свойства столбца** установите для свойства <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> значение `true`.  
  
    > [!NOTE]
    >  Заморозить столбец можно также при его добавлении, выбрав параметр **Зафиксированный** в диалоговом окне **Добавление столбца**.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)   
 [How to: Display Right\-to\-Left Text in Windows Forms for Globalization](http://msdn.microsoft.com/ru-ru/f0663385-2354-4c65-8676-706422283b14)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)