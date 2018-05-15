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
ms.openlocfilehash: 015e93fb551b8d48b8a57662b8def61c3cb46c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="cf3b2-102">Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем</span><span class="sxs-lookup"><span data-stu-id="cf3b2-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="cf3b2-103">Панели элемента <xref:System.Windows.Forms.SplitContainer> управления поддаются, размеров и управлению пользователями.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="cf3b2-104">Однако будет время, если требуется программно управлять разделителем, где он расположен и определить, каким образом можно переместить.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="cf3b2-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> И других свойствах на <xref:System.Windows.Forms.SplitContainer> управления позволяют точно контролировать поведение пользовательского интерфейса в соответствии с потребностями.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="cf3b2-106">Эти свойства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="cf3b2-107">name</span><span class="sxs-lookup"><span data-stu-id="cf3b2-107">Name</span></span>|<span data-ttu-id="cf3b2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cf3b2-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="cf3b2-109">Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A></span><span class="sxs-lookup"><span data-stu-id="cf3b2-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="cf3b2-110">Определяет, является ли разделитель при помощи клавиатуры или мыши.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="cf3b2-111">Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A></span><span class="sxs-lookup"><span data-stu-id="cf3b2-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="cf3b2-112">Определяет расстояние в пикселях от левой или верхней границы для перемещаемой полосы-разделителя.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="cf3b2-113">Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A></span><span class="sxs-lookup"><span data-stu-id="cf3b2-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="cf3b2-114">Определяет минимальное расстояние в пикселях, что разделитель может быть перемещен пользователем.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="cf3b2-115">Следующий пример изменяет <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство для создания эффекта «привязка разделитель»; когда пользователь перетаскивает разделитель, увеличивается в единицах 10 точек, а не значение по умолчанию 1.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="cf3b2-116">Чтобы определить режим изменения размера SplitContainer</span><span class="sxs-lookup"><span data-stu-id="cf3b2-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="cf3b2-117">В процедуре, задайте <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> свойство до нужного размера, чтобы достичь поведение разделителя «привязка».</span><span class="sxs-lookup"><span data-stu-id="cf3b2-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="cf3b2-118">В следующем примере кода в форме <xref:System.Windows.Forms.Form.Load> событий, разделителя в <xref:System.Windows.Forms.SplitContainer> перехода 10 пикселей при перетаскивании элемента управления имеет значение.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
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
  
     <span data-ttu-id="cf3b2-119">(Visual C#) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="cf3b2-120">Плавное перемещение разделителя влево или вправо не будет действовать ощутимого; Тем не менее когда указатель мыши выходит 10 точек в любом направлении, разделитель будет привязана к новой позиции.</span><span class="sxs-lookup"><span data-stu-id="cf3b2-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3b2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cf3b2-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
