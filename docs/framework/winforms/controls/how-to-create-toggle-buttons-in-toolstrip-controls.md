---
title: "Практическое руководство. Создание переключателей в элементах управления ToolStrip | Microsoft Docs"
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
  - "примеры [Windows Forms], панели инструментов"
  - "переключатели, создание"
  - "ToolStrip - элемент управления [Windows Forms], создание выключателей"
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание переключателей в элементах управления ToolStrip
Когда пользователь щелкает переключатель, он отображается углубленным и остается таковым до повторного щелчка.  
  
### Для создания переключателя ToolStripButton выполните следующие действия.  
  
-   Используйте код, такой как в следующем примере.  В этом коде предполагается, что форма содержит элемент управления <xref:System.Windows.Forms.ToolStrip> и что коллекция <xref:System.Windows.Forms.ToolStrip.Items%2A> содержит <xref:System.Windows.Forms.ToolStripButton> с именем `toolStripButton1`.  Также предполагается, что обработчик событий с именем `toolStripButton1_CheckedChanged` уже существует.  
  
     \[Visual Basic\]  
  
    ```  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripButton>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)