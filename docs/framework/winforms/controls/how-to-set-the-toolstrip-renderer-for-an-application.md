---
title: "Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения | Microsoft Docs"
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
  - "MenuStrip - элемент управления [Windows Forms]"
  - "Renderer - свойство [Windows Forms]"
  - "панели инструментов [Windows Forms], настройка"
  - "ToolStrip - элемент управления [Windows Forms]"
  - "ToolStripProfessionalRenderer - класс [Windows Forms]"
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения
Настройка внешнего вида элементов управления <xref:System.Windows.Forms.ToolStrip> может производиться отдельно для каждого из них или для всех элементов управления <xref:System.Windows.Forms.ToolStrip>, используемых в приложении.  
  
## Пример  
 В примере кода ниже показано, как выборочно применить пользовательское средство отрисовки к элементу управления <xref:System.Windows.Forms.ToolStrip> и элементу управления <xref:System.Windows.Forms.MenuStrip>.  
  
 Чтобы использовать этот пример, скомпилируйте и запустите приложение, а затем выберите область пользовательской отрисовки в элементе управления <xref:System.Windows.Forms.ComboBox>.  Нажмите **Применить**, чтобы задать средство отрисовки.  
  
 Чтобы увидеть пользовательскую отрисовку элемента меню, в элементе управления <xref:System.Windows.Forms.ComboBox> выберите пункт <xref:System.Windows.Forms.MenuStrip>, нажмите **Применить**, а затем выберите пункт меню **Файл**.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Чтобы применить пользовательское средство отрисовки ко всем элементам управления <xref:System.Windows.Forms.ToolStrip>, используемым в приложении, задайте свойство <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>.  
  
 Чтобы применить пользовательское средство отрисовки к отдельному элементу управления <xref:System.Windows.Forms.ToolStrip>, задайте свойство <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>.  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)