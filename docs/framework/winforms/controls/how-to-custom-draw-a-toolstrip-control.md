---
title: Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: a9f603efdb4b4a5f68154da9c6a8bd05b55b8f46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182212"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="9ea50-102">Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9ea50-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="9ea50-103">Элементы управления <xref:System.Windows.Forms.ToolStrip> имеют следующие связанные классы отрисовки:</span><span class="sxs-lookup"><span data-stu-id="9ea50-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
- <span data-ttu-id="9ea50-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> предоставляет внешний вид и стиль операционной системы;</span><span class="sxs-lookup"><span data-stu-id="9ea50-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
- <span data-ttu-id="9ea50-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> предоставляет внешний вид и стиль Microsoft Office;</span><span class="sxs-lookup"><span data-stu-id="9ea50-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
- <span data-ttu-id="9ea50-106"><xref:System.Windows.Forms.ToolStripRenderer> является абстрактным базовым классом для двух других классов отрисовки.</span><span class="sxs-lookup"><span data-stu-id="9ea50-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="9ea50-107">Для настраиваемой отрисовки (также известной как рисование владельцем) элемента управления <xref:System.Windows.Forms.ToolStrip> можно переопределить один из классов отрисовки и изменить перспективу логики отрисовки.</span><span class="sxs-lookup"><span data-stu-id="9ea50-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="9ea50-108">В приведенных ниже процедурах описаны различные аспекты настраиваемой отрисовки.</span><span class="sxs-lookup"><span data-stu-id="9ea50-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="9ea50-109">Переключение между доступными средствами отрисовки</span><span class="sxs-lookup"><span data-stu-id="9ea50-109">To switch between the provided renderers</span></span>  
  
- <span data-ttu-id="9ea50-110">Задайте для свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> требуемое значение <xref:System.Windows.Forms.ToolStripRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="9ea50-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="9ea50-111">Для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> статический режим <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> определяет средство отрисовки для приложения.</span><span class="sxs-lookup"><span data-stu-id="9ea50-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="9ea50-112">Другие значения <xref:System.Windows.Forms.ToolStripRenderMode>: <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> и <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="9ea50-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="9ea50-113">Изменение границ в стиле Microsoft Office на прямые</span><span class="sxs-lookup"><span data-stu-id="9ea50-113">To change the Microsoft Office–style borders to straight</span></span>  
  
- <span data-ttu-id="9ea50-114">Переопределите <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, но не вызывайте базовый класс.</span><span class="sxs-lookup"><span data-stu-id="9ea50-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ea50-115">Существуют версии этого метода для <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="9ea50-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="9ea50-116">Изменение ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="9ea50-116">To change the ProfessionalColorTable</span></span>  
  
- <span data-ttu-id="9ea50-117">Переопределите <xref:System.Windows.Forms.ProfessionalColorTable> и измените нужные цвета.</span><span class="sxs-lookup"><span data-stu-id="9ea50-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="9ea50-118">Изменение отрисовки для всех элементов управления ToolStrip в приложении</span><span class="sxs-lookup"><span data-stu-id="9ea50-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1. <span data-ttu-id="9ea50-119">С помощью свойства <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> выберите одно из доступных средств отрисовки.</span><span class="sxs-lookup"><span data-stu-id="9ea50-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="9ea50-120">Используйте <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> для назначения пользовательского средства отрисовки.</span><span class="sxs-lookup"><span data-stu-id="9ea50-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="9ea50-121">Убедитесь в том, что свойству <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> присвоено значение по умолчанию <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="9ea50-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="9ea50-122">Отключение цветов в стиле Microsoft Office для всего приложения</span><span class="sxs-lookup"><span data-stu-id="9ea50-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
- <span data-ttu-id="9ea50-123">Присвойте параметру <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9ea50-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="9ea50-124">Отключение цветов в стиле Microsoft Office для одного элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9ea50-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
- <span data-ttu-id="9ea50-125">Используйте код, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="9ea50-125">Use code similar to the following code example.</span></span>  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9ea50-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ea50-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="9ea50-127">Элементы управления со встроенной поддержкой рисования владельцем</span><span class="sxs-lookup"><span data-stu-id="9ea50-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="9ea50-128">Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ea50-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="9ea50-129">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9ea50-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
