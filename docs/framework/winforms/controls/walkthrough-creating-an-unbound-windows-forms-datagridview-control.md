---
title: "Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms"
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
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2c57cfbab4d3af6cebff96517383999ae5b73d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms
Часто можно отображать табличные данные, получен не из базы данных. Например может потребоваться отобразить содержимое двухмерного массива строк. <xref:System.Windows.Forms.DataGridView> Класс предоставляет удобный и настраиваемый способ отображения данных без привязки к источнику данных. В этом пошаговом руководстве показано, как для заполнения <xref:System.Windows.Forms.DataGridView> для управления добавлением и удалением строк в режиме «свободный». По умолчанию пользователь может добавлять новые строки. Чтобы запретить добавление строк, задайте <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> свойство `false`.  
  
 Скопируйте код из этой темы, в разделе [как: создание свободного элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Для использования свободного элемента управления DataGridView  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит следующие объявления переменных и `Main` метод.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Реализуйте `SetupLayout` метод в определении класса формы для настройки макета.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Создание `SetupDataGridView` метод для настройки <xref:System.Windows.Forms.DataGridView> столбцы и свойства.  
  
     Этот метод сначала добавляет <xref:System.Windows.Forms.DataGridView> на форму элемент управления <xref:System.Windows.Forms.Control.Controls%2A> коллекции. Далее число столбцов для отображения задается с помощью <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> свойство. Стиль по умолчанию для заголовков столбцов задается <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, и <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> свойства <xref:System.Windows.Forms.DataGridViewCellStyle> возвращенных <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> свойство.  
  
     Задания свойства макета и внешнего вида, а затем присваиваются имена столбцов. Когда этот метод завершает работу, <xref:System.Windows.Forms.DataGridView> управления готов к заполнению.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Создание `PopulateDataGridView` метод для добавления строк <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
     Каждая строка представляет песню и связанные сведения.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  С помощью вспомогательных методов можно присоединить обработчики событий.  
  
     Будет обрабатывать **добавить** и **удаление** кнопок <xref:System.Windows.Forms.Control.Click> событий, формы <xref:System.Windows.Forms.Form.Load> события и <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.CellFormatting> событий.  
  
     Когда **добавить** кнопки <xref:System.Windows.Forms.Control.Click> события новая пустая строка добавляется <xref:System.Windows.Forms.DataGridView>.  
  
     Когда **удаление** кнопки <xref:System.Windows.Forms.Control.Click> события, удалить выбранную строку, если это не строка для новых записей, которая позволяет пользователю добавлять новые строки. Эта строка всегда является последней строки в <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
     Когда формы <xref:System.Windows.Forms.Form.Load> события `SetupLayout`, `SetupDataGridView`, и `PopulateDataGridView` вызываются вспомогательные методы.  
  
     Когда <xref:System.Windows.Forms.DataGridView.CellFormatting> события, каждая ячейка в `Date` столбец представляется в формате длинной даты, если не удается выполнить синтаксический анализ значения ячейки.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.  
  
#### <a name="to-test-the-form"></a>Чтобы проверить форму  
  
-   Нажмите клавишу F5 для запуска приложения.  
  
     Вы увидите <xref:System.Windows.Forms.DataGridView> управления, отображающий музыкальные файлы, перечисленные в `PopulateDataGridView`. Можно добавлять новые строки с **добавить строку** кнопки и удалять выбранные строки с **удалить строку** кнопки. Свободные <xref:System.Windows.Forms.DataGridView> управления хранилищем данных и его данные не зависят от внешних источников, таких как <xref:System.Data.DataSet> или массив.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Это приложение позволяет основные <xref:System.Windows.Forms.DataGridView> возможности элемента управления. Можно настроить внешний вид и поведение <xref:System.Windows.Forms.DataGridView> управления несколькими способами:  
  
-   Изменение стилей границ и заголовка. Дополнительные сведения см. в разделе [как: изменения границ и стили линий сетки в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Включения или отключения пользовательского ввода для <xref:System.Windows.Forms.DataGridView> элемента управления. Дополнительные сведения см. в разделе [как: запретить добавление и удаление строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), и [как: сделать столбцы только для чтения в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Проверьте входные данные пользователя для ошибки, относящиеся к базе данных. Дополнительные сведения см. в разделе [Пошаговое руководство: обработка ошибок, связанных с вводом данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Обработка очень больших наборов данных в виртуальном режиме. Дополнительные сведения см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Настройте внешний вид ячеек. Дополнительные сведения см. в разделе [как: Настройка внешнего вида ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) и [как: набор стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
