---
title: "Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], всплывающие подсказки"
  - "ToolTip - компонент [Windows Forms], значения задержки"
  - "всплывающие подсказки [Windows Forms], значения задержки"
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms
Для компонента Windows Forms <xref:System.Windows.Forms.ToolTip> можно задать несколько значений задержек.  Все эти значения выражаются в миллисекундах.  Свойство <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> определяет, как долго пользователь должен удерживать указатель мыши над элементом управления, чтобы появилась строка ToolTip.  Свойство <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> задает время в миллисекундах, через которое появляются следующие строки ToolTip после перемещения указателя мыши на другой элемент управления.  Свойство <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> определяет продолжительность показа строки ToolTip.  Можно задать каждое из этих значений по отдельности или присвоить значение только свойству <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, остальные задержки устанавливаются на основе значения свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>.  Например, если свойство <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> имеет значение N, то свойству <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> присваивается значение N, свойству <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> — значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, деленное на пять \(N\/5\), а свойству <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> — значение, в пять раз большее значения свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> \(5N\).  
  
### Чтобы задать значение задержки  
  
1.  Задайте следующие значения свойств, как показано в примере.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## См. также  
 [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)