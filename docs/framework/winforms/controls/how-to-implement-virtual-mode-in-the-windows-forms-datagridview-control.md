---
title: "Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "данные [Windows Forms], управление большими наборами данных"
  - "DataGridView - элемент управления [Windows Forms], большие наборы данных"
  - "DataGridView - элемент управления [Windows Forms], виртуальный режим"
  - "виртуальный режим"
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms
В примере кода ниже показано, как управлять большими наборами данных с помощью элемента управления <xref:System.Windows.Forms.DataGridView>, свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> которого присвоено значение `true`.  
  
 Полное описание этого примера кода см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## Пример  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>   
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>   
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>   
 <xref:System.Windows.Forms.DataGridView.RowValidated>   
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>   
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>   
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>   
 [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)