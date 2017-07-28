---
title: "Пример. Проверка данных элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "данные [Windows Forms], проверка"
  - "таблицы данных, проверка данных"
  - "проверка данных, Windows Forms"
  - "DataGridView - элемент управления [Windows Forms], проверка данных"
  - "проверка данных, Windows Forms"
  - "пошаговые руководства [Windows Forms], DataGridView - элемент управления"
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Пример. Проверка данных элемента управления DataGridView в Windows Forms
При отображении функциональных возможностей ввода данных на экране для пользователя введенные в форму данные можно, как правило, проверить.  С помощью класса <xref:System.Windows.Forms.DataGridView> можно легко проверить данные, прежде чем они будут записаны в хранилище данных.  Для проверки данных можно обработать событие <xref:System.Windows.Forms.DataGridView.CellValidating>, вызываемое <xref:System.Windows.Forms.DataGridView> при изменении текущей ячейки.  
  
 В этом пошаговом руководстве будут извлечены строки из таблицы `Customers` в примере базы данных "Northwind", которые затем будут выведены в элементе управления <xref:System.Windows.Forms.DataGridView>.  Когда пользователь изменяет ячейку в столбце `CompanyName` и пытается выйти из нее, обработчик событий <xref:System.Windows.Forms.DataGridView.CellValidating> проверяет новую строку наименования компании на наличие данных в ней; если значение в строке отсутствует, <xref:System.Windows.Forms.DataGridView>,  не позволяет курсору перемещаться их ячейки до тех пор, пока значение в ячейке не будет указано.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Доступ к серверу с примером базы данных SQL Server под именем "Northwind".  
  
## Создание формы  
  
#### Проверка данных, введенных в элемент управления DataGridView  
  
1.  Создайте производный от <xref:System.Windows.Forms.Form> класс, который содержит элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource>.  
  
     В следующем примере кода представлена базовая реализация и включен метод `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки подробных сведений для подключения к базе данных.  
  
     В этом примере кода используется метод `GetData` , возвращающий заполненный объект <xref:System.Data.DataTable>.  Переменной `connectionString` следует присвоить значение, подходящее для базы данных.  
  
    > [!IMPORTANT]
    >  Хранение в строке подключения конфиденциальных сведений, таких как пароль, может привести к снижению уровня защиты приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Дополнительные сведения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, инициализирующий <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и устанавливающий привязку данных.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Реализуйте обработчики для событий <xref:System.Windows.Forms.DataGridView.CellValidating> и <xref:System.Windows.Forms.DataGridView.CellEndEdit> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
     В обработчике событий <xref:System.Windows.Forms.DataGridView.CellValidating> определяется, будет ли значение ячейки в столбце `CompanyName` пустым.  Если ячейка не проходит проверку, свойству <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> класса <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=fullName> необходимо присвоить значение `true`.  В этом случае элемент управления <xref:System.Windows.Forms.DataGridView> заставит курсор остаться в ячейке.  Свойству <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> в строке присвойте пояснительную строку.  В этом случае на экране появится значок ошибки с ToolTip с текстом ошибки.  В обработчике событий <xref:System.Windows.Forms.DataGridView.CellEndEdit> свойству <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> строки присвойте пустую строку.  Событие <xref:System.Windows.Forms.DataGridView.CellEndEdit> происходит только при выходе ячейки из режима редактирования, и если ячейка не проходит проверку, режим редактирования не отключается.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Скомпилируйте и запустите приложение.  
  
     Появится элемент управления <xref:System.Windows.Forms.DataGridView> с данными из таблицы `Customers`.  Если дважды щелкнуть ячейку в столбце `CompanyName`, значение можно будет изменить.  Если удалить все символы и нажать клавишу TAB для выхода из ячейки, <xref:System.Windows.Forms.DataGridView> не позволит выйти из нее.  Если в ячейку ввести непустое строковое значение, элемент управления <xref:System.Windows.Forms.DataGridView> позволит выйти из ячейки.  
  
## Следующие действия  
 Это приложение позволяет в общем понять возможности элемента управления <xref:System.Windows.Forms.DataGridView>.  Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно контролировать несколькими способами.  
  
-   Изменение стилей границ и заголовка.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Разрешение или ограничение пользовательского ввода в элемент управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения см. в разделах [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) и [Практическое руководство. Определение столбцов элемента управления DataGridView как доступных только для чтения в Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверка ввода пользователя на наличие ошибок, связанных с базой данных.  Дополнительные сведения см. в разделе [Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме.  Дополнительные сведения см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройка внешнего вида ячеек.  Дополнительные сведения см. в разделах [Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [Практическое руководство. Настройка шрифтов и цветов в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)   
 [Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)