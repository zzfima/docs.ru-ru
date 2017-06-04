---
title: "Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, значения по умолчанию для новых строк"
  - "DataGridView - элемент управления [Windows Forms], ввод данных"
  - "DataGridView - элемент управления [Windows Forms], значения по умолчанию для новых строк"
  - "строки, задание значений по умолчанию"
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms
Ввод данных упрощается, если приложение заполняет добавляемые строки значениями по умолчанию.  Благодаря классу <xref:System.Windows.Forms.DataGridView> можно заполнять строки значениями по умолчанию с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  Это событие наступает при входе пользователя в строку для добавления новых записей.    С помощью обработчика этого события можно заполнить требуемые ячейки любыми значениями.  
  
 В следующем примере кода демонстрируется способ задания значений по умолчаний для новых строк с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`.  
  
-   Функция `NewCustomerId` для генерации уникальных значений для ячеек столбца `CustomerID`.  
  
-   Ссылки на сборки <xref:System?displayProperty=fullName> и <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Ввод данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)