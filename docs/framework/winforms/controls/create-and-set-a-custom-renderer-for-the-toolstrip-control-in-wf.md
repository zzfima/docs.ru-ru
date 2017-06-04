---
title: "Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms | Microsoft Docs"
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
  - "панели инструментов [Windows Forms], отрисовка"
  - "ToolStrip - элемент управления [Windows Forms], пользовательская отрисовка"
  - "ToolStrip - элемент управления [Windows Forms], отрисовка"
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
Элементы управления <xref:System.Windows.Forms.ToolStrip> обеспечивают удобную поддержку тем и стилей.  Присвоив свойству <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> или <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> пользовательское средство отрисовки, можно настроить внешний вид и поведение произвольным образом.  
  
 Можно назначить средства отрисовки каждому отдельному элементу <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip> или <xref:System.Windows.Forms.StatusStrip>, либо можно задать средство отрисовки для всех объектов с помощью свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>, указав <xref:System.Windows.Forms.ToolStripRenderMode?displayProperty=fullName> в качестве значения свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> возвращает значение <xref:System.Windows.Forms.ToolStripRenderMode>, только если значение свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> отлично от `null`.  
  
### Создание пользовательского средства отрисовки  
  
1.  Создайте расширение класса <xref:System.Windows.Forms.ToolStripRenderer>.  
  
2.  Создайте пользовательское средство отрисовки путем переопределения соответствующих членов *On…*.  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
  
    ```  
  
     \[C\#\]  
  
    ```  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
  
    ```  
  
### Установка настраиваемого средства отрисвоки в качестве текущего  
  
1.  Чтобы применить пользовательское средство отрисовки к отдельному элементу управления <xref:System.Windows.Forms.ToolStrip>, задайте средство отрисовки в качестве значения свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.Renderer = new RedTextRenderer();  
  
    ```  
  
2.  Чтобы применить пользовательское средство отрисовки ко всем классам <xref:System.Windows.Forms.ToolStrip>, используемым в приложении, задайте средство отрисовки в качестве значения свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>, а свойству <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> присвойте значение <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)