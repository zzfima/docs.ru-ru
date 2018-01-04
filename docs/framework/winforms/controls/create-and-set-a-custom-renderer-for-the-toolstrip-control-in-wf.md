---
title: "Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad328af3aed9a319fe80d829b9556e867533e601
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
<xref:System.Windows.Forms.ToolStrip>элементы управления обеспечивают удобную поддержку тем и стилей. Полностью настраиваемый внешний вид и поведение (Вид) можно добиться путем задания либо <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> свойство или <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> свойства пользовательского средства отрисовки.  
  
 Модули подготовки отчетов можно назначить для каждого отдельного <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, или <xref:System.Windows.Forms.StatusStrip> управления, или же можно использовать <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> влияют на все объекты, задав свойству <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> свойства <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>Возвращает <xref:System.Windows.Forms.ToolStripRenderMode.Custom> только тогда, когда значение <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> не `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Создание пользовательского средства отрисовки  
  
1.  Расширить <xref:System.Windows.Forms.ToolStripRenderer> класса.  
  
2.  Реализуйте требуемого пользовательское средство отрисовки путем переопределения соответствующих *на...* члены  
  
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
  
    ```csharp  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Чтобы задать пользовательское средство отрисовки для текущего модуля подготовки отчетов  
  
1.  Чтобы задать пользовательское средство отрисовки для одного <xref:System.Windows.Forms.ToolStrip>, задайте <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> свойства пользовательского средства отрисовки.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  Или задать пользовательское средство отрисовки для всех <xref:System.Windows.Forms.ToolStrip> классы, содержащиеся в приложении: задать <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> свойство пользовательского средства отрисовки и установите <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> свойства <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
