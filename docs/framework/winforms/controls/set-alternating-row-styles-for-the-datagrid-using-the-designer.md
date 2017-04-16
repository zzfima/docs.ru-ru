---
title: "Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "данные [Windows Forms], отображение"
  - "DataGridView - элемент управления [Windows Forms], изменение стиля строки"
  - "форматы бухгалтерской книги"
  - "строки, изменение"
  - "Windows Forms, строки"
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора
Данные в таблицах часто представлены в формате, подобном бухгалтерским книгам: в чередующихся строках используется разный цвет фона.  Применение такого формата позволяет проще определять, какие ячейки находятся в какой строке; это особенно удобно в широких таблицах со множеством столбцов.  
  
 С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно указать полные сведения о стиле для чередующихся строк.  Для различения чередующихся строк можно использовать такие характеристики стиля, как цвет фона, цвет текста и начертание шрифта.  Дополнительные сведения см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Определение стилей для чередующихся строк  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.DataGridView> в конструкторе.  
  
2.  В окне **Свойства** нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом со свойством <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>.  
  
3.  В диалоговом окне **Построитель стиля ячеек** определите стиль путем установки свойств, используйте область **Предварительный просмотр** для подтверждения выбранных настроек.  Выбранный стиль применяется для каждой второй строки, отображаемой в элементе управления, начиная со второй строки.  
  
4.  Чтобы определить стили для остальных строк, повторите шаги 2 и 3 с помощью свойства <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.  
  
    > [!NOTE]
    >  При отображении ячеек используются стили, унаследованные от различных свойств.  Дополнительные сведения о наследовании стилей см. в разделе [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Базовое форматирование и оформление элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Использование конструктора с элементом управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)