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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="3dbb3-102">Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3dbb3-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="3dbb3-103"><xref:System.Windows.Forms.ToolStrip>элементы управления дают легкую поддержку темам и стилям.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="3dbb3-104">Вы можете достичь полностью пользовательский внешний вид <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> и поведение <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> (смотреть и чувствовать), установив либо свойство или свойство пользовательских рендеров.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="3dbb3-105">Вы можете назначить рендеры <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>каждому <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> человеку, <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStrip>или управления, или вы можете использовать свойство, чтобы повлиять на все объекты, установив свойство.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dbb3-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>возвращается <xref:System.Windows.Forms.ToolStripRenderMode.Custom> только в <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> том `null`случае, если стоимость не является.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="3dbb3-107">Создание пользовательского рендерера</span><span class="sxs-lookup"><span data-stu-id="3dbb3-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="3dbb3-108">Расширьте <xref:System.Windows.Forms.ToolStripRenderer> класс.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="3dbb3-109">Реализация желаемого пользовательского рендеринга, переопределяя соответствующие *On...*</span><span class="sxs-lookup"><span data-stu-id="3dbb3-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="3dbb3-110">members</span><span class="sxs-lookup"><span data-stu-id="3dbb3-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="3dbb3-111">Установить пользовательский рендерер в текущем рендере</span><span class="sxs-lookup"><span data-stu-id="3dbb3-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="3dbb3-112">Чтобы установить пользовательский <xref:System.Windows.Forms.ToolStrip>рендер <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> для одного, установите свойство к пользовательскому рендереру.</span><span class="sxs-lookup"><span data-stu-id="3dbb3-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="3dbb3-113">Или установить пользовательский рендер для <xref:System.Windows.Forms.ToolStrip> всех классов, <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> содержащихся в приложении: <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Установите свойство в пользовательском рендере редераторе и установите свойство для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode></span><span class="sxs-lookup"><span data-stu-id="3dbb3-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3dbb3-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3dbb3-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="3dbb3-115">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3dbb3-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="3dbb3-116">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3dbb3-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="3dbb3-117">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3dbb3-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
