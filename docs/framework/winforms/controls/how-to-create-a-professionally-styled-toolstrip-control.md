---
title: "Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip | Microsoft Docs"
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
  - "панели инструментов [Windows Forms]"
  - "ToolStrip - элемент управления [Windows Forms]"
  - "ToolStripProfessionalRenderer - класс [Windows Forms]"
  - "ToolStripRenderer - класс [Windows Forms]"
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip
Вы можете придать элементам управления <xref:System.Windows.Forms.ToolStrip> своего приложения профессиональный внешний вид и поведение, создав собственный класс, производный от типа <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] эта возможность поддерживается довольно широко.  
  
 См. раздел [Пример. Создание профессионально оформленного элемента управления ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## Пример  
 В следующем примере кода демонстрируется использование элементов управления <xref:System.Windows.Forms.ToolStrip> для создания составного элемента управления, напоминающего **область переходов** в Microsoft® Outlook®.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Пример. Создание профессионально оформленного элемента управления ToolStrip](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Практическое руководство. Связывание с формой стандартных элементов меню](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)