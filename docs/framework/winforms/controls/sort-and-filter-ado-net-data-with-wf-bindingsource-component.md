---
title: "Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms | Microsoft Docs"
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
  - "ADO.NET [Windows Forms]"
  - "BindingSource - компонент [Windows Forms], сортировка и фильтрация данных"
  - "данные [Windows Forms], фильтрация"
  - "данные [Windows Forms], сортировка"
  - "сортировка данных, ADO.NET"
  - "фильтрация [Windows Forms], ADO.NET"
  - "сортировка данных"
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms
Возможности сортировки и фильтрации элемента управления <xref:System.Windows.Forms.BindingSource> можно предоставить приложениям с помощью свойств <xref:System.Windows.Forms.BindingSource.Sort%2A> и <xref:System.Windows.Forms.BindingSource.Filter%2A>.  Если базовый источник данных представляет собой <xref:System.ComponentModel.IBindingList>, может использоваться простая сортировка; если же источник данных представляет собой <xref:System.ComponentModel.IBindingListView>, может использоваться фильтрация и расширенная сортировка.  Свойство <xref:System.Windows.Forms.BindingSource.Sort%2A> требует использования стандартного синтаксиса [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]: строка, представляющая собой имя столбца данных в источнике данных, после которой ставится `ASC` или `DESC` для указания на порядок сортировки списка по возрастанию или убыванию.  При задании расширенной сортировки или сортировки по нескольким столбцам столбцы отделяются запятыми\-разделителями.  Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A> принимает в качестве значения строковое выражение.  
  
> [!NOTE]
>  Хранение в строке подключения конфиденциальных сведений, таких как пароль, может привести к снижению уровня защиты приложения.  Использование проверки подлинности Windows \(также называемой встроенными средствами безопасности\) — более безопасный способ управления доступом к базе данных.  Дополнительные сведения см. в разделе [Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### Фильтрация данных с помощью BindingSource  
  
-   Присвойте свойству <xref:System.Windows.Forms.BindingSource.Filter%2A> в качестве значения необходимое выражение.  
  
     В следующем примере кода выражение представляет собой имя столбца, после которого указано требуемое для столбца значение.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### Сортировка данных с помощью BindingSource  
  
1.  Присвойте свойству <xref:System.Windows.Forms.BindingSource.Sort%2A> в качестве значения необходимое имя столбца, после которого укажите `ASC` или `DESC`, чтобы задать порядок сортировки по возрастанию или убыванию.  
  
2.  Несколько столбцов разделяются запятыми.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## Пример  
 В следующем примере кода производится загрузка данных из таблицы "Customers" демонстрационной базы данных "Northwind" в элемент управления <xref:System.Windows.Forms.DataGridView> с последующей фильтрацией и сортировкой отображаемых данных.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## Компиляция кода  
 Для выполнения кода данного примера скопируйте его в форму, содержащую элемент управления <xref:System.Windows.Forms.BindingSource> с именем `BindingSource1` и элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  Создайте обработчик событий <xref:System.Windows.Forms.Form.Load> для формы и вызовите `InitializeSortedFilteredBindingSource` в методе обработчика событий загрузки.  
  
## См. также  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>   
 <xref:System.Windows.Forms.BindingSource.Filter%2A>   
 [Практическое руководство. Установка образцов баз данных](../Topic/How%20to:%20Install%20Sample%20Databases.md)   
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)