---
title: "Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView - элемент управления [Windows Forms], форм с отношением "главный-подчиненный""
  - "списки типа "основной-подробности", отображение в формах Windows Forms"
  - "таблицы с отношением подчинения, отображение в формах Windows Forms"
  - "пошаговые руководства [Windows Forms], DataGridView - элемент управления"
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms
Одним из наиболее распространенных случаев использования элемента управления <xref:System.Windows.Forms.DataGridView> является использование *главного и подчиненного* представлений данных, в котором отображается отношение родитель\/потомок между двумя таблицами базы данных.  При выборе строк в главной таблице соответствующие дочерние данные обновляются в дочерней таблице.  
  
 Реализация главного и дочернего представлений данных легко выполняется за счет взаимодействия между элементом управления <xref:System.Windows.Forms.DataGridView> и компонентом <xref:System.Windows.Forms.BindingSource> .  В этом пошаговом руководстве будет выполнена привязка формы с использованием двух элементов управления <xref:System.Windows.Forms.DataGridView> и двух компонентов <xref:System.Windows.Forms.BindingSource>.  В форме будут показаны две связанные таблицы из примера базы данных SQL Server "Northwind": `Customers` и `Orders`.  По окончании будет готова форма, где все клиенты в базе данных будут показаны в главном представлении <xref:System.Windows.Forms.DataGridView> а все заказы по выбранному клиенту – в подчиненном представлении <xref:System.Windows.Forms.DataGridView>.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Доступ к серверу с примером базы данных SQL Server под именем "Northwind".  
  
## Создание формы  
  
#### Создание главного и подчиненного представлений  
  
1.  Создайте производный от <xref:System.Windows.Forms.Form> класс, который содержит два элемента управления <xref:System.Windows.Forms.DataGridView> и два компонента <xref:System.Windows.Forms.BindingSource>.  В следующем коде представлена базовая реализация формы и включен метод `Main`.  Если для создания формы используется конструктор [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], то вместо кода этого примера можно использовать созданный конструктором код. При этом следует использовать имена, указанные в объявлениях переменных в этом примере.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Реализуйте метод в определении класса формы для обработки подчиненного представления для подключения к базе данных.  В этом примере используется метод `GetData`, который заполняет объект <xref:System.Data.DataSet> , добавляет объект <xref:System.Data.DataRelation> в набор данных и привязывает компоненты <xref:System.Windows.Forms.BindingSource>.  Переменной `connectionString` следует присвоить значение, подходящее для базы данных.  
  
    > [!IMPORTANT]
    >  Хранение в строке подключения конфиденциальных сведений, таких как пароль, может привести к снижению уровня защиты приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Дополнительные сведения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load>, которое привязывает элементы управления <xref:System.Windows.Forms.DataGridView> к компонентам <xref:System.Windows.Forms.BindingSource> и вызовите метод `GetData`.  Следующий пример содержит код, который изменяет размеры столбцов <xref:System.Windows.Forms.DataGridView>, чтобы вместить отображаемые данные.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Скомпилируйте и запустите приложение.  
  
     Появится два элемента управления <xref:System.Windows.Forms.DataGridView>, расположенные друг над другом.  В верхнем элементе управления показаны клиенты `Customers` из таблицы "Northwind", а в нижнем – `Orders`, соответствующие выбранному клиенту.  По мере выбора строк в верхнем элементе управления <xref:System.Windows.Forms.DataGridView>, содержимое нижнего элемента управления <xref:System.Windows.Forms.DataGridView> изменяется соответствующим образом.  
  
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
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)   
 [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)