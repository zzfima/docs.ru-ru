---
title: "Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c602af6799da57fec904c87da7bed77c0040eff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms
Обработка ошибок из базового хранилища данных является обязательной функцией приложения ввода данных. Windows Forms <xref:System.Windows.Forms.DataGridView> управления упрощает этот процесс, предоставляя <xref:System.Windows.Forms.DataGridView.DataError> событие, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правила.  
  
 В этом пошаговом руководстве будет извлекать строки из `Customers` таблицы в базе данных Northwind и отобразить их в <xref:System.Windows.Forms.DataGridView> элемента управления. Если дубликат `CustomerID` значение обнаруживается в новой строке или измененной существующей строке <xref:System.Windows.Forms.DataGridView.DataError> происходит событие, которое будет обработано, отображая <xref:System.Windows.Forms.MessageBox> с описанием исключения.  
  
 Скопируйте код из этой темы, в разделе [как: обработки ошибок, возникает во время ввода данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Доступ к серверу с учебной базе данных "Борей" SQL Server.  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Обработка ошибок ввода данных в элементе управления DataGridView  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит <xref:System.Windows.Forms.DataGridView> управления и <xref:System.Windows.Forms.BindingSource> компонента.  
  
     В следующем примере кода представлена базовая реализация и включает в себя `Main` метод.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки сведения о подключении к базе данных.  
  
     Этот пример кода использует `GetData` метод, возвращающий заполненный <xref:System.Data.DataTable> объекта. Убедитесь, что значение `connectionString` переменной значение, соответствующее базе данных.  
  
    > [!IMPORTANT]
    >  Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Реализуйте обработчик для формы <xref:System.Windows.Forms.Form.Load> событие, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и задает привязку данных.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Обрабатывать <xref:System.Windows.Forms.DataGridView.DataError> события <xref:System.Windows.Forms.DataGridView>.  
  
     Если контекст ошибки операции фиксации, выведите ошибку в <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.  
  
#### <a name="to-test-the-form"></a>Чтобы проверить форму  
  
-   Нажмите клавишу F5 для запуска приложения.  
  
     Вы увидите <xref:System.Windows.Forms.DataGridView> заполнения элемента управления данными из таблицы Customers. При вводе повторяющиеся значения для `CustomerID` и фиксации изменения, будет автоматически восстановлено значение ячейки, и вы увидите <xref:System.Windows.Forms.MessageBox> с указанием ошибки ввода данных.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Это приложение позволяет основные <xref:System.Windows.Forms.DataGridView> возможности элемента управления. Можно настроить внешний вид и поведение <xref:System.Windows.Forms.DataGridView> управления несколькими способами:  
  
-   Изменение стилей границ и заголовка. Дополнительные сведения см. в разделе [как: изменения границ и стили линий сетки в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Включения или отключения пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления. Дополнительные сведения см. в разделе [как: запретить добавление и удаление строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), и [как: сделать столбцы только для чтения в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверка пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления. Дополнительные сведения см. в разделе [Пошаговое руководство: проверка данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме. Дополнительные сведения см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройте внешний вид ячеек. Дополнительные сведения см. в разделе [как: Настройка внешнего вида ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [как: набор стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Пример. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md)
