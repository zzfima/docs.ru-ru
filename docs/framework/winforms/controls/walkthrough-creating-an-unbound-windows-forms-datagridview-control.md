---
title: "Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "данные [Windows Forms], отображение без привязки к источнику данных"
  - "данные [Windows Forms], несвязанный"
  - "DataGridView - элемент управления [Windows Forms], отображение данных без привязки к источнику данных"
  - "DataGridView - элемент управления [Windows Forms], несвязанные данные"
  - "пошаговые руководства [Windows Forms], DataGridView - элемент управления"
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms
Иногда требуется отображать табличные данные, полученные не из базы данных.  Например, может потребоваться отобразить содержимое двухмерного массива строк.  Класс <xref:System.Windows.Forms.DataGridView> предоставляет удобный и настраиваемый способ отображения данных без привязки к источнику данных.  Данное руководство включает сведения о том, как заполнить элемент управления <xref:System.Windows.Forms.DataGridView> и управлять добавлением и удалением строк в "непривязанном" режиме.  По умолчанию пользователь может добавлять новые строки.  Чтобы запретить добавление строк, свойству <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> следует присвоить значение `false`.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## Создание формы  
  
#### Использование элемента управления DataGridView без привязки к данным  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий следующие объявления переменных и метод `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Реализуйте метод `SetupLayout` в определении класса формы для настройки макета формы.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Создайте метод `SetupDataGridView` для настройки столбцов и свойств <xref:System.Windows.Forms.DataGridView>.  
  
     Этот метод сначала добавляет элемент управления <xref:System.Windows.Forms.DataGridView> в коллекцию формы <xref:System.Windows.Forms.Control.Controls%2A>.  Затем определяется число отображаемых столбцов при помощи свойства <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>.  Стиль заголовков столбцов по умолчанию определяется путем задания значений свойств <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> и <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращенного свойством <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>.  
  
     Сначала устанавливаются свойства макета и внешнего вида, затем назначаются названия столбцов.  При выходе этого метода элемент управления <xref:System.Windows.Forms.DataGridView> готов к заполнению.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Создайте метод `PopulateDataGridView` для добавления строк в элемент управления <xref:System.Windows.Forms.DataGridView>.  
  
     Каждая строка представляет песню и связанные с ней данные.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  При наличии вспомогательных методов можно присоединить обработчики событий.  
  
     Мы будем обрабатывать события <xref:System.Windows.Forms.Control.Click> кнопок **Добавить** и **Удалить**, события формы <xref:System.Windows.Forms.Form.Load> и события <xref:System.Windows.Forms.DataGridView.CellFormatting> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
     При возникновении события <xref:System.Windows.Forms.Control.Click> кнопки **Добавить** новая пустая строка добавляется в <xref:System.Windows.Forms.DataGridView>.  
  
     При возникновении события <xref:System.Windows.Forms.Control.Click> кнопки **Удалить** удаляется выбранная строка, если это не строка для ввода новых записей, которая служит для добавления новых строк.  Эта строка всегда является последней в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
     При возникновении события формы <xref:System.Windows.Forms.Form.Load> вызываются вспомогательные методы `SetupLayout`, `SetupDataGridView` и `PopulateDataGridView`.  
  
     При возникновении события <xref:System.Windows.Forms.DataGridView.CellFormatting> каждая ячейка в столбце `Date` использует длинный формат даты, за исключением случаев, когда не удается разобрать значение в ячейке.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Нажмите клавишу F5 для запуска приложения.  
  
     Появится элемент управления <xref:System.Windows.Forms.DataGridView> с песнями, перечисленными в `PopulateDataGridView`.  Можно добавлять новые строки с помощью кнопки **Добавить строку** и удалять выбранные строки с помощью кнопки **Удалить строку**.  Элемент управления <xref:System.Windows.Forms.DataGridView> служит хранилищем данных, его данные не зависят от внешних источников, таких как <xref:System.Data.DataSet> или массивы.  
  
## Следующие действия  
 Это приложение позволяет в общем понять возможности элемента управления <xref:System.Windows.Forms.DataGridView>.  Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно контролировать несколькими способами.  
  
-   Изменение стилей границ и заголовка.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Разрешение или ограничение пользовательского ввода в элемент управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения см. в разделах [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) и [Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверка ввода пользователя на наличие ошибок, связанных с базой данных.  Дополнительные сведения см. в разделе [Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме.  Дополнительные сведения см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройка внешнего вида ячеек.  Дополнительные сведения см. в разделах [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)   
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)