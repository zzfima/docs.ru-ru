---
title: "Пошаговое руководство: Создание основной подробности формы с помощью двух элементов управления DataGridView Windows Forms"
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
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d213d70d6f12cb8b574f07457c1b20317670d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms
Одним из наиболее распространенных сценариев использования <xref:System.Windows.Forms.DataGridView> управления *иерархического* формы, в котором отображается отношение "родители потомки" между двумя таблицами базы данных. Выбор строк в главной таблице приводит таблицы сведений, чтобы обновить соответствующие дочерние данные.  
  
 Реализация главного и подчиненного облегчает взаимодействие между <xref:System.Windows.Forms.DataGridView> управления и <xref:System.Windows.Forms.BindingSource> компонента. В этом пошаговом руководстве вы создадите формы, с использованием двух <xref:System.Windows.Forms.DataGridView> элементов управления и два <xref:System.Windows.Forms.BindingSource> компонентов. В форме будут показаны две связанные таблицы в образце базы данных "Борей" SQL Server: `Customers` и `Orders`. Когда вы закончите, будет иметь форму, которая содержит все клиенты базы данных в базе данных master <xref:System.Windows.Forms.DataGridView> и все заказы для выбранного клиента подробно <xref:System.Windows.Forms.DataGridView>.  
  
 Скопируйте код из этой темы, в разделе [как: создание Главная и подчиненная формы с помощью двух DataGridView элементов управления Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Доступ к серверу с учебной базе данных "Борей" SQL Server.  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-create-a-masterdetail-form"></a>Создание главного и подчиненного  
  
1.  Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержит два <xref:System.Windows.Forms.DataGridView> элементов управления и два <xref:System.Windows.Forms.BindingSource> компонентов. Ниже представлена базовая реализация формы и включает `Main` метод. Если вы используете [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] конструктора для создания формы, можно использовать вместо этого кода конструктора созданный код, но следует использовать названия из объявления переменных.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки подробные сведения о подключении к базе данных. В этом примере используется `GetData` метод, который заполняет <xref:System.Data.DataSet> , добавляет <xref:System.Data.DataRelation> объекта для набора данных и привязывает <xref:System.Windows.Forms.BindingSource> компонентов. Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.  
  
    > [!IMPORTANT]
    >  Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Реализуйте обработчик для формы <xref:System.Windows.Forms.Form.Load> событий, который привязывает <xref:System.Windows.Forms.DataGridView> элементы управления <xref:System.Windows.Forms.BindingSource> компоненты и вызывает метод `GetData` метод. Следующий пример содержит код, который изменяет размер <xref:System.Windows.Forms.DataGridView> столбцы по размеру отображаемых данных.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться в том, что оно правильно работает.  
  
#### <a name="to-test-the-form"></a>Чтобы проверить форму  
  
-   Скомпилируйте и запустите приложение.  
  
     Вы увидите два <xref:System.Windows.Forms.DataGridView> управляет друг с другом. В верхней части являются клиентов из базы данных Northwind `Customers` таблицы, а в нижней — `Orders` соответствующего выбранному клиенту. При выборе различными строками в правом верхнем <xref:System.Windows.Forms.DataGridView>, содержимое нижнего <xref:System.Windows.Forms.DataGridView> соответствующим образом изменить.  
  
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
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md)
