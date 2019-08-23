---
title: Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
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
ms.openlocfilehash: c354ace3a7d3ce43f549dd1295a85fbee004eb22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929732"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
<xref:System.Windows.Forms.ToolStrip>элементы управления обеспечивают простую поддержку тем и стилей. Можно добиться абсолютного внешнего вида и поведения (внешнего вида), задав <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> для свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> или свойства настраиваемый модуль подготовки отчетов.  
  
 Можно назначить модули подготовки отчетов каждому отдельному <xref:System.Windows.Forms.ToolStrip>элементу <xref:System.Windows.Forms.ContextMenuStrip>управления, <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> или, либо <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> можно использовать свойство, чтобы повлиять на все объекты, задав для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>свойства значение.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>Возвращает <xref:System.Windows.Forms.ToolStripRenderMode.Custom> <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> , только если значение параметра не равно `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Создание пользовательского модуля подготовки отчетов  
  
1. <xref:System.Windows.Forms.ToolStripRenderer> Расширьте класс.  
  
2. Реализуйте требуемую пользовательскую отрисовку, переопределив подходящую *для...* члены  
  
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
  
1. Чтобы задать пользовательский модуль подготовки отчетов для одного <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> задайте для свойства настраиваемый модуль подготовки отчетов.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Или, чтобы задать пользовательский модуль подготовки отчетов для <xref:System.Windows.Forms.ToolStrip> всех классов, содержащихся в приложении: <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Присвойте <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> свойству настраиваемый модуль подготовки отчетов и присвойте свойству значение.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
