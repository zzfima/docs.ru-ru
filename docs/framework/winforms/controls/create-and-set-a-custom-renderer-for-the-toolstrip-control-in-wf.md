---
title: Как создать и задать пользовательский модуль отрисовки для элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743420"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
<xref:System.Windows.Forms.ToolStrip> элементы управления обеспечивают простую поддержку тем и стилей. Можно добиться абсолютного внешнего вида и поведения (внешнего вида), задав для свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> или свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> настраиваемый модуль подготовки отчетов.  
  
 Можно назначать модули подготовки отчетов каждому отдельному <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>или <xref:System.Windows.Forms.StatusStrip> или использовать свойство <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> для влияния на все объекты, установив для свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> значение <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> возвращает <xref:System.Windows.Forms.ToolStripRenderMode.Custom> только в том случае, если значение <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> не `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Создание пользовательского модуля подготовки отчетов  
  
1. Расширьте класс <xref:System.Windows.Forms.ToolStripRenderer>.  
  
2. Реализуйте требуемую пользовательскую отрисовку, переопределив подходящую *для...* members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Задание пользовательского модуля подготовки отчетов в качестве текущего модуля подготовки отчетов  
  
1. Чтобы задать пользовательский модуль подготовки отчетов для одного <xref:System.Windows.Forms.ToolStrip>, задайте для свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> настраиваемый модуль подготовки отчетов.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Или, чтобы задать пользовательский модуль подготовки отчетов для всех <xref:System.Windows.Forms.ToolStrip> классов, содержащихся в приложении: задайте для свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> настраиваемый модуль подготовки отчетов и задайте для свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> значение <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
