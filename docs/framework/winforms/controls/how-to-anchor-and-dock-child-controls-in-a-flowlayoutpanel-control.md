---
title: "Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel | Microsoft Docs"
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
  - "дочерние элементы управления, привязка и закрепление"
  - "элементы управления [Windows Forms], дочерний"
  - "FlowLayoutPanel - элемент управления [Windows Forms], дочерние элементы управления"
  - "макет [Windows Forms], дочерние элементы управления"
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel
Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> поддерживает свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> в своих дочерних элементах управления.  
  
### Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel  
  
1.  Создание элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> в форме.  
  
2.  Присвойте <xref:System.Windows.Forms.Control.Width%2A> для элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> значение 300 и для <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> значение <xref:System.Windows.Forms.FlowDirection>.  
  
3.  Создайте два элемента управления <xref:System.Windows.Forms.Button> и поместите их в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
4.  Присвойте свойству <xref:System.Windows.Forms.Control.Width%2A> первой кнопки значение 200.  
  
5.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> первой кнопки значение <xref:System.Windows.Forms.DockStyle>.  
  
    > [!NOTE]
    >  Вторая кнопка принимает ту же ширину, что и первая кнопка.  Она не растягивается по ширине элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> второй кнопки значение `Нет`.  При этом кнопка примет исходную ширину.  
  
7.  Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> второй кнопки значение `Слева, справа`.  
  
    > [!IMPORTANT]
    >  Вторая кнопка принимает ту же ширину, что и первая кнопка.  Она не растягивается по ширине элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  Общее правило для привязки и закрепления в элементе управления <xref:System.Windows.Forms.FlowLayoutPanel>: в вертикальном направлении элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> вычисляет ширину предполагаемого столбца исходя из ширины самого широкого элемента управления в столбце.  Другие элементы управления в этом столбце со свойствами <xref:System.Windows.Forms.Control.Anchor%2A> или <xref:System.Windows.Forms.Control.Dock%2A> выравниваются или растягиваются до этого предполагаемого столбца.  Аналогичное поведение работает и в горизонтальном направлении.  Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> вычисляет высоту предполагаемой строки на основе самого высокого дочернего элемента управления в строке, и все закрепленные или привязанные дочерние элементы управления в этой строке выравниваются или их размеры устанавливаются в соответствии с предполагаемой строкой.  
  
## Пример  
 На следующем рисунке показаны четыре кнопки, привязанный и закрепленные по отношению к синей кнопке в <xref:System.Windows.Forms.FlowLayoutPanel>.  Значение параметра <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> — <xref:System.Windows.Forms.FlowDirection>.  
  
 ![Закрепление FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/net-flpanchorexp.png "NET\_FLPanchorExp")  
  
 На следующем рисунке показаны четыре кнопки, привязанные и закрепленные по отношению к синей кнопке в <xref:System.Windows.Forms.FlowLayoutPanel>.  Значение параметра <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> — <xref:System.Windows.Forms.FlowDirection>.  
  
 ![Закрепление FlowLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-flpanchor2.png "VS\_FLPanchor2")  
  
 В следующем примере кода демонстрируются все варианты свойства <xref:System.Windows.Forms.Control.Anchor%2A> для размещения элемента управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Дополнительные сведения о построении данного примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] представлены в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Данный пример можно также построить в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] путем вставки кода в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 [Общие сведения об элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-overview.md)