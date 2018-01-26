---
title: "Пример. Проверка данных элемента управления DataGridView в Windows Forms"
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
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2ede616b311119d174534e53cb3aaf9e366c7c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Пример. Проверка данных элемента управления DataGridView в Windows Forms
При отображении функциональных возможностей ввода данных, пользователям необходимо часто проверки данных, введенных в форму. <xref:System.Windows.Forms.DataGridView> Класс предоставляет удобный способ выполнять проверку перед данные передаются в хранилище данных. Вы можете проверять данные, обрабатывая <xref:System.Windows.Forms.DataGridView.CellValidating> событие, которое вызывается <xref:System.Windows.Forms.DataGridView> при изменении текущей ячейки.  
  
 В этом пошаговом руководстве будет извлекать строки из `Customers` таблицы в базе данных Northwind и отобразить их в <xref:System.Windows.Forms.DataGridView> элемента управления. При редактировании ячейки в `CompanyName` столбца и пытается оставить ячейку, <xref:System.Windows.Forms.DataGridView.CellValidating> обработчик событий проверяет новая строка названия компании, чтобы убедиться, что она не пуста; Если новое значение является пустой строкой, <xref:System.Windows.Forms.DataGridView> сделает невозможным курсору из ячейки до введения непустой строкой.  
  
 Скопируйте код из этой темы, в разделе [как: проверка данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Доступ к серверу с учебной базе данных "Борей" SQL Server.  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>Чтобы проверить данные, введенные в элементе управления DataGridView  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит <xref:System.Windows.Forms.DataGridView> управления и <xref:System.Windows.Forms.BindingSource> компонента.  
  
     В следующем примере кода представлена базовая реализация и включает в себя `Main` метод.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки сведения о подключении к базе данных.  
  
     Этот пример кода использует `GetData` метод, возвращающий заполненный <xref:System.Data.DataTable> объекта. Убедитесь, что значение `connectionString` переменной значение, соответствующее базе данных.  
  
    > [!IMPORTANT]
    >  Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows, также известные как встроенная безопасность является более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Реализуйте обработчик для формы <xref:System.Windows.Forms.Form.Load> событие, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и задает привязку данных.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Реализовать обработчики для <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.CellValidating> и <xref:System.Windows.Forms.DataGridView.CellEndEdit> события.  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating> Обработчик событий —, где можно определить, является ли значение ячейки в `CompanyName` столбец пуст. Если значение ячейки не проходит проверку, задайте <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> свойство <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> класса `true`. В результате <xref:System.Windows.Forms.DataGridView> элемента управления для предотвращения курсор остаться в ячейке. Задать <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> пояснительного строку в строке. Это показывает значок ошибки с всплывающей подсказки, содержащей текст ошибки. В <xref:System.Windows.Forms.DataGridView.CellEndEdit> задать обработчик событий <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> в строке на пустую строку. <xref:System.Windows.Forms.DataGridView.CellEndEdit> Событие возникает, только когда ячейка выходит из режим редактирования, если она не проходит проверку.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.  
  
#### <a name="to-test-the-form"></a>Чтобы проверить форму  
  
-   Скомпилируйте и запустите приложение.  
  
     Вы увидите <xref:System.Windows.Forms.DataGridView> с данными из `Customers` таблицы. Если дважды щелкнуть ячейку в `CompanyName` столбца, можно изменить значение. Если удалить все символы и нажать клавишу TAB, чтобы выйти из ячейки, <xref:System.Windows.Forms.DataGridView> предотвращает выход. При вводе непустой строкой в ячейке, <xref:System.Windows.Forms.DataGridView> управления служит для выхода из ячейки.  
  
## <a name="next-steps"></a>Следующие шаги  
 Это приложение позволяет основные <xref:System.Windows.Forms.DataGridView> возможности элемента управления. Можно настроить внешний вид и поведение <xref:System.Windows.Forms.DataGridView> управления несколькими способами:  
  
-   Изменение стилей границ и заголовка. Дополнительные сведения см. в разделе [как: изменения границ и стили линий сетки в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Включения или отключения пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления. Дополнительные сведения см. в разделе [как: запретить добавление и удаление строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), и [как: сделать столбцы только для чтения в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверьте входные данные пользователя для ошибки, относящиеся к базе данных. Дополнительные сведения см. в разделе [Пошаговое руководство: обработка ошибок, связанных с вводом данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме. Дополнительные сведения см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройте внешний вид ячеек. Дополнительные сведения см. в разделе [как: Настройка внешнего вида ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [как: набор шрифтов и цветов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Проверка данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [Пошаговое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md)
