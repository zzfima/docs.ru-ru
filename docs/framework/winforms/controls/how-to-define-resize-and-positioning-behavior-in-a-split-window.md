---
title: Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 4ed1d2a5230502bc598906da0db5164396986e66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217072"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="11dd4-102">Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем</span><span class="sxs-lookup"><span data-stu-id="11dd4-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="11dd4-103">Панели элемента <xref:System.Windows.Forms.SplitContainer> управления поддаются, размеров и управлению пользователями.</span><span class="sxs-lookup"><span data-stu-id="11dd4-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="11dd4-104">Тем не менее, будет существовать раз, когда необходимо программно управлять разделителем, где он размещается, и определить, каким образом его можно переместить.</span><span class="sxs-lookup"><span data-stu-id="11dd4-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="11dd4-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Свойства и другие свойства <xref:System.Windows.Forms.SplitContainer> управления позволяют точно контролировать поведение пользовательского интерфейса в соответствии с потребностями.</span><span class="sxs-lookup"><span data-stu-id="11dd4-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="11dd4-106">Эти свойства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="11dd4-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="11dd4-107">name</span><span class="sxs-lookup"><span data-stu-id="11dd4-107">Name</span></span>|<span data-ttu-id="11dd4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="11dd4-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> <span data-ttu-id="11dd4-109">свойство;</span><span class="sxs-lookup"><span data-stu-id="11dd4-109">property</span></span>|<span data-ttu-id="11dd4-110">Определяет, является ли разделитель при помощи клавиатуры или мыши.</span><span class="sxs-lookup"><span data-stu-id="11dd4-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> <span data-ttu-id="11dd4-111">свойство;</span><span class="sxs-lookup"><span data-stu-id="11dd4-111">property</span></span>|<span data-ttu-id="11dd4-112">Определяет расстояние в пикселях от левого или верхнего края для перемещаемой полосы-разделителя.</span><span class="sxs-lookup"><span data-stu-id="11dd4-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> <span data-ttu-id="11dd4-113">свойство;</span><span class="sxs-lookup"><span data-stu-id="11dd4-113">property</span></span>|<span data-ttu-id="11dd4-114">Определяет минимальное расстояние в пикселях, что разделитель может быть перемещен пользователем.</span><span class="sxs-lookup"><span data-stu-id="11dd4-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="11dd4-115">Следующий пример изменяет <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство для создания эффекта «привязка разделителем»; когда пользователь перетаскивает разделитель, увеличивается в единицах 10 пикселей, а не по умолчанию 1.</span><span class="sxs-lookup"><span data-stu-id="11dd4-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="11dd4-116">Для определения поведения размера SplitContainer</span><span class="sxs-lookup"><span data-stu-id="11dd4-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="11dd4-117">В процедуре, задайте <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство до нужного размера, таким образом, чтобы реализовать поведение «привязка» разделителя.</span><span class="sxs-lookup"><span data-stu-id="11dd4-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="11dd4-118">В следующем примере кода, в форме <xref:System.Windows.Forms.Form.Load> событие, разделителя в <xref:System.Windows.Forms.SplitContainer> элемента управления задано значение для перехода 10 пикселей при перетаскивании.</span><span class="sxs-lookup"><span data-stu-id="11dd4-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="11dd4-119">(Visual C#) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="11dd4-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="11dd4-120">Плавное перемещение влево или вправо разделителя не будет действовать ощутимого; Тем не менее когда указатель мыши выходит 10 точек в любом направлении, разделитель будет привязана к новой позиции.</span><span class="sxs-lookup"><span data-stu-id="11dd4-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11dd4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="11dd4-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
