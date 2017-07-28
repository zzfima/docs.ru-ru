---
title: "Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], удаление"
  - "DataGridView - элемент управления [Windows Forms], удаление столбцов"
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms
Если элемент управления <xref:System.Windows.Forms.DataGridView> настроен на автоматическую генерацию своих столбцов на основе данных из источника данных, определенные столбцы можно опустить на выбор.  Это можно сделать, вызвав метод <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> в коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>.  Кроме того, столбцы можно скрыть из виду, присвоив свойству <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> значение `false`.  Этот способ помогает, когда при определенных условиях требуется отобразить скрытые столбцы или когда необходим доступ к данным в столбцах без их отображения.  
  
### Удаление автоматически сгенерированных столбцов  
  
-   Вызовите метод <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### Скрытие автоматически сгенерированных столбцов  
  
-   Свойству <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> столбца присвойте значение `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, привязанный к таблице со столбцами `Fax` и `CustomerID`, например таблица `Customers` или пример базы данных "Northwind".  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)