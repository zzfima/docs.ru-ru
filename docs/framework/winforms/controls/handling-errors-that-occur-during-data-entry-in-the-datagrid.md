---
title: "Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms | Microsoft Docs"
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
  - "ввод данных, обработка ошибок"
  - "таблицы данных, обработка ошибок"
  - "DataGridView - элемент управления [Windows Forms], обработка ошибок"
  - "обработка ошибок, ввод данных"
  - "обработка ошибок, DataGridView - элемент управления"
  - "пошаговые руководства [Windows Forms], DataGridView - элемент управления"
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms
Обработка ошибок для базового хранилища данных является обязательной функцией приложения ввода данных.  Элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> упрощает обработку ошибок путем предоставления события <xref:System.Windows.Forms.DataGridView.DataError>, инициируемого при обнаружении нарушения ограничения или бизнес\-правила в хранилище данных.  
  
 В этом пошаговом руководстве будут извлечены строки из таблицы `Customers` в примере базы данных "Northwind", которые затем будут выведены в элементе управления <xref:System.Windows.Forms.DataGridView>.  При обнаружении повторяющегося значения `CustomerID` в новой строке или измененной существующей строке произойдет событие <xref:System.Windows.Forms.DataGridView.DataError>, которое будет обработано отображением <xref:System.Windows.Forms.MessageBox> с описанием исключения.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Доступ к серверу с примером базы данных SQL Server под именем "Northwind".  
  
## Создание формы  
  
#### Обработка ошибок ввода данных в элементе управления DataGridView  
  
1.  Создайте производный от <xref:System.Windows.Forms.Form> класс, который содержит элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource>.  
  
     В следующем примере кода представлена базовая реализация и включен метод `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки подробных сведений для подключения к базе данных.  
  
     В этом примере кода используется метод `GetData` , возвращающий заполненный объект <xref:System.Data.DataTable>.  Переменной `connectionString` следует присвоить значение, подходящее для базы данных.  
  
    > [!IMPORTANT]
    >  Хранение в строке подключения конфиденциальных сведений, таких как пароль, может привести к снижению уровня защиты приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Дополнительные сведения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, инициализирующий <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и устанавливающий привязку данных.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Обработайте событие <xref:System.Windows.Forms.DataGridView.DataError> в <xref:System.Windows.Forms.DataGridView>.  
  
     Если контекстом ошибки является операция фиксации, выведите ошибку в <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Нажмите клавишу F5 для запуска приложения.  
  
     Появится элемент управления <xref:System.Windows.Forms.DataGridView> с данными из таблицы Customers.  При вводе повторяющегося значения `CustomerID` и фиксации изменения, значение в ячейке будет автоматически восстановлено и на экране появится <xref:System.Windows.Forms.MessageBox> с указанием ошибки ввода данных.  
  
## Следующие действия  
 Это приложение позволяет в общем понять возможности элемента управления <xref:System.Windows.Forms.DataGridView>.  Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно контролировать несколькими способами.  
  
-   Изменение стилей границ и заголовка.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Разрешение или ограничение пользовательского ввода в элемент управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения см. в разделах [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) и [Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверка пользовательского ввода в элементе управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения см. в разделе [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме.  Дополнительные сведения см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройка внешнего вида ячеек.  Дополнительные сведения см. в разделах [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)