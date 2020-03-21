---
title: 'Как: Создать и установить пользовательский рендерер для управления ToolStrip'
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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182408"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms
<xref:System.Windows.Forms.ToolStrip>элементы управления дают легкую поддержку темам и стилям. Вы можете достичь полностью пользовательский внешний вид <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> и поведение <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> (смотреть и чувствовать), установив либо свойство или свойство пользовательских рендеров.  
  
 Вы можете назначить рендеры <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>каждому <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> человеку, <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStrip>или управления, или вы можете использовать свойство, чтобы повлиять на все объекты, установив свойство.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>возвращается <xref:System.Windows.Forms.ToolStripRenderMode.Custom> только в <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> том `null`случае, если стоимость не является.  
  
### <a name="to-create-a-custom-renderer"></a>Создание пользовательского рендерера  
  
1. Расширьте <xref:System.Windows.Forms.ToolStripRenderer> класс.  
  
2. Реализация желаемого пользовательского рендеринга, переопределяя соответствующие *On...* members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Установить пользовательский рендерер в текущем рендере  
  
1. Чтобы установить пользовательский <xref:System.Windows.Forms.ToolStrip>рендер <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> для одного, установите свойство к пользовательскому рендереру.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. Или установить пользовательский рендер для <xref:System.Windows.Forms.ToolStrip> всех классов, <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> содержащихся в приложении: <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Установите свойство в пользовательском рендере редераторе и установите свойство для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>  
  
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
