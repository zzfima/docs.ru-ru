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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="0f21f-102">Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f21f-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="0f21f-103"><xref:System.Windows.Forms.ToolStrip>элементы управления обеспечивают простую поддержку тем и стилей.</span><span class="sxs-lookup"><span data-stu-id="0f21f-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="0f21f-104">Можно добиться абсолютного внешнего вида и поведения (внешнего вида), задав <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> для свойства <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> или свойства настраиваемый модуль подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="0f21f-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="0f21f-105">Можно назначить модули подготовки отчетов каждому отдельному <xref:System.Windows.Forms.ToolStrip>элементу <xref:System.Windows.Forms.ContextMenuStrip>управления, <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> или, либо <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> можно использовать свойство, чтобы повлиять на все объекты, задав для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>свойства значение.</span><span class="sxs-lookup"><span data-stu-id="0f21f-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f21f-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>Возвращает <xref:System.Windows.Forms.ToolStripRenderMode.Custom> <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> , только если значение параметра не равно `null`.</span><span class="sxs-lookup"><span data-stu-id="0f21f-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="0f21f-107">Создание пользовательского модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="0f21f-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="0f21f-108"><xref:System.Windows.Forms.ToolStripRenderer> Расширьте класс.</span><span class="sxs-lookup"><span data-stu-id="0f21f-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="0f21f-109">Реализуйте требуемую пользовательскую отрисовку, переопределив подходящую *для...*</span><span class="sxs-lookup"><span data-stu-id="0f21f-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="0f21f-110">члены</span><span class="sxs-lookup"><span data-stu-id="0f21f-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="0f21f-111">Задание пользовательского модуля подготовки отчетов в качестве текущего модуля подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="0f21f-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="0f21f-112">Чтобы задать пользовательский модуль подготовки отчетов для одного <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> задайте для свойства настраиваемый модуль подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="0f21f-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="0f21f-113">Или, чтобы задать пользовательский модуль подготовки отчетов для <xref:System.Windows.Forms.ToolStrip> всех классов, содержащихся в приложении: <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>Присвойте <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> свойству настраиваемый модуль подготовки отчетов и присвойте свойству значение.</span><span class="sxs-lookup"><span data-stu-id="0f21f-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0f21f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0f21f-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="0f21f-115">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0f21f-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="0f21f-116">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0f21f-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="0f21f-117">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0f21f-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
