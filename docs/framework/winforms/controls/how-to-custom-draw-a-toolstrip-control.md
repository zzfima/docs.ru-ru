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
ms.openlocfilehash: 74092fdcd72c09670db53dc79d43d9d52f0dcf4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172191"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="aa06b-102">Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa06b-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="aa06b-103">Элементы управления <xref:System.Windows.Forms.ToolStrip> имеют следующие связанные классы отрисовки:</span><span class="sxs-lookup"><span data-stu-id="aa06b-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> <span data-ttu-id="aa06b-104">предоставляет внешний вид и стиль операционной системы.</span><span class="sxs-lookup"><span data-stu-id="aa06b-104">provides the appearance and style of your operating system.</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <span data-ttu-id="aa06b-105">предоставляет внешний вид и стиль Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="aa06b-105">provides the appearance and style of Microsoft Office.</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> <span data-ttu-id="aa06b-106">является абстрактным базовым классом для двух других классов отрисовки.</span><span class="sxs-lookup"><span data-stu-id="aa06b-106">is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="aa06b-107">Для настраиваемой отрисовки (также известной как рисование владельцем) элемента управления <xref:System.Windows.Forms.ToolStrip> можно переопределить один из классов отрисовки и изменить перспективу логики отрисовки.</span><span class="sxs-lookup"><span data-stu-id="aa06b-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="aa06b-108">В приведенных ниже процедурах описаны различные аспекты настраиваемой отрисовки.</span><span class="sxs-lookup"><span data-stu-id="aa06b-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="aa06b-109">Переключение между доступными средствами отрисовки</span><span class="sxs-lookup"><span data-stu-id="aa06b-109">To switch between the provided renderers</span></span>  
  
-   <span data-ttu-id="aa06b-110">Задайте для свойства <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> требуемое значение <xref:System.Windows.Forms.ToolStripRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="aa06b-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="aa06b-111">Для <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> статический режим <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> определяет средство отрисовки для приложения.</span><span class="sxs-lookup"><span data-stu-id="aa06b-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="aa06b-112">Другие значения <xref:System.Windows.Forms.ToolStripRenderMode>: <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> и <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="aa06b-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="aa06b-113">Изменение границ в стиле Microsoft Office на прямые</span><span class="sxs-lookup"><span data-stu-id="aa06b-113">To change the Microsoft Office–style borders to straight</span></span>  
  
-   <span data-ttu-id="aa06b-114">Переопределите <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, но не вызывайте базовый класс.</span><span class="sxs-lookup"><span data-stu-id="aa06b-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa06b-115">Существуют версии этого метода для <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="aa06b-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="aa06b-116">Изменение ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="aa06b-116">To change the ProfessionalColorTable</span></span>  
  
-   <span data-ttu-id="aa06b-117">Переопределите <xref:System.Windows.Forms.ProfessionalColorTable> и измените нужные цвета.</span><span class="sxs-lookup"><span data-stu-id="aa06b-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
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
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="aa06b-118">Изменение отрисовки для всех элементов управления ToolStrip в приложении</span><span class="sxs-lookup"><span data-stu-id="aa06b-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1.  <span data-ttu-id="aa06b-119">С помощью свойства <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> выберите одно из доступных средств отрисовки.</span><span class="sxs-lookup"><span data-stu-id="aa06b-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2.  <span data-ttu-id="aa06b-120">Используйте <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> для назначения пользовательского средства отрисовки.</span><span class="sxs-lookup"><span data-stu-id="aa06b-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3.  <span data-ttu-id="aa06b-121">Убедитесь в том, что свойству <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> присвоено значение по умолчанию <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="aa06b-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="aa06b-122">Отключение цветов в стиле Microsoft Office для всего приложения</span><span class="sxs-lookup"><span data-stu-id="aa06b-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
-   <span data-ttu-id="aa06b-123">Присвойте свойству <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="aa06b-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="aa06b-124">Отключение цветов в стиле Microsoft Office для одного элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa06b-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
-   <span data-ttu-id="aa06b-125">Используйте код, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="aa06b-125">Use code similar to the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa06b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="aa06b-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="aa06b-127">Элементы управления Windows Forms со встроенной поддержки рисования владельцем</span><span class="sxs-lookup"><span data-stu-id="aa06b-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="aa06b-128">Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aa06b-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="aa06b-129">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa06b-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
