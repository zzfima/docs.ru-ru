---
title: События мыши в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 671e37c7d6dc40046d6d717d7785b03b6b545c7e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333682"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="a5489-102">События мыши в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5489-102">Mouse Events in Windows Forms</span></span>
<span data-ttu-id="a5489-103">При обработке ввода данных с помощью мыши обычно необходимо знать положение указателя и состояние кнопок мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="a5489-104">В этом разделе приводится подробная информация о получении этих сведений из событий мыши и описывается порядок, в котором вызываются события щелчка мыши в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5489-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="a5489-105">Список и описание всех событий мыши, см. в разделе [принцип работы мыши ввода в Windows Forms](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a5489-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="a5489-106">Также см. в разделе [Обзор обработчиков событий (Windows Forms)](event-handlers-overview-windows-forms.md) и [Общие сведения о событиях (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a5489-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>  
  
## <a name="mouse-information"></a><span data-ttu-id="a5489-107">Сведения о мыши</span><span class="sxs-lookup"><span data-stu-id="a5489-107">Mouse Information</span></span>  
 <span data-ttu-id="a5489-108">Объект <xref:System.Windows.Forms.MouseEventArgs> отправляется обработчикам событий мыши, связанных с нажатием кнопки мыши и отслеживанием ее движений.</span><span class="sxs-lookup"><span data-stu-id="a5489-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <xref:System.Windows.Forms.MouseEventArgs> <span data-ttu-id="a5489-109">сведения о текущем состоянии мыши, включая положение указателя мыши в клиентских координатах, какие кнопки мыши, а ли прокрутке колесика мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-109">provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="a5489-110">Некоторые события мыши, например те, которые просто уведомляют о том, что указатель мыши пересек границы элемента управления, отправляют обработчику событий объект <xref:System.EventArgs> без подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="a5489-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>  
  
 <span data-ttu-id="a5489-111">Если нужно знать текущее состояние кнопок мыши или положение ее указателя, но при этом избежать обработки события мыши, можно также использовать свойства <xref:System.Windows.Forms.Control.MouseButtons%2A> и <xref:System.Windows.Forms.Control.MousePosition%2A> класса <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="a5489-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <xref:System.Windows.Forms.Control.MouseButtons%2A> <span data-ttu-id="a5489-112">Возвращает сведения о том, какие кнопки мыши нажаты в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a5489-112">returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="a5489-113">Свойство <xref:System.Windows.Forms.Control.MousePosition%2A> возвращает экранные координаты указателя мыши, которые эквивалентны значению, возвращаемому методом <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5489-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>  
  
## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="a5489-114">Преобразование между экранными и клиентскими координатами</span><span class="sxs-lookup"><span data-stu-id="a5489-114">Converting Between Screen and Client Coordinates</span></span>  
 <span data-ttu-id="a5489-115">Так как некоторые сведения о положении мыши представлены в клиентских координатах, а другие — в экранных, может потребоваться преобразовать точку из одной системы координат в другую.</span><span class="sxs-lookup"><span data-stu-id="a5489-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="a5489-116">Это легко сделать с помощью методов <xref:System.Windows.Forms.Control.PointToClient%2A> и <xref:System.Windows.Forms.Control.PointToScreen%2A>, доступных в классе <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="a5489-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>  
  
## <a name="standard-click-event-behavior"></a><span data-ttu-id="a5489-117">Стандартное поведение события щелчка</span><span class="sxs-lookup"><span data-stu-id="a5489-117">Standard Click Event Behavior</span></span>  
 <span data-ttu-id="a5489-118">Если требуется обрабатывать события щелчка мыши в определенном порядке, необходимо знать порядок, в котором вызываются события щелчка в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5489-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="a5489-119">Когда кнопка мыши (любая) нажимается и отпускается, все элементы управления Windows Forms, кроме отмеченных в списке ниже, вызывают события щелчка в одном и том же порядке.</span><span class="sxs-lookup"><span data-stu-id="a5489-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="a5489-120">Ниже приведен порядок событий, вызываемых одинарным щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-120">The following list shows the order of events raised for a single mouse-button click:</span></span>  
  
1. <xref:System.Windows.Forms.Control.MouseDown> <span data-ttu-id="a5489-121">.</span><span class="sxs-lookup"><span data-stu-id="a5489-121">event.</span></span>  
  
2. <xref:System.Windows.Forms.Control.Click> <span data-ttu-id="a5489-122">.</span><span class="sxs-lookup"><span data-stu-id="a5489-122">event.</span></span>  
  
3. <xref:System.Windows.Forms.Control.MouseClick> <span data-ttu-id="a5489-123">.</span><span class="sxs-lookup"><span data-stu-id="a5489-123">event.</span></span>  
  
4. <xref:System.Windows.Forms.Control.MouseUp> <span data-ttu-id="a5489-124">.</span><span class="sxs-lookup"><span data-stu-id="a5489-124">event.</span></span>  
  
 <span data-ttu-id="a5489-125">Ниже приведен порядок событий, вызываемых двойным щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-125">Following is the order of events raised for a double mouse-button click:</span></span>  
  
1. <xref:System.Windows.Forms.Control.MouseDown> <span data-ttu-id="a5489-126">.</span><span class="sxs-lookup"><span data-stu-id="a5489-126">event.</span></span>  
  
2. <xref:System.Windows.Forms.Control.Click> <span data-ttu-id="a5489-127">.</span><span class="sxs-lookup"><span data-stu-id="a5489-127">event.</span></span>  
  
3. <xref:System.Windows.Forms.Control.MouseClick> <span data-ttu-id="a5489-128">.</span><span class="sxs-lookup"><span data-stu-id="a5489-128">event.</span></span>  
  
4. <xref:System.Windows.Forms.Control.MouseUp> <span data-ttu-id="a5489-129">.</span><span class="sxs-lookup"><span data-stu-id="a5489-129">event.</span></span>  
  
5. <xref:System.Windows.Forms.Control.MouseDown> <span data-ttu-id="a5489-130">.</span><span class="sxs-lookup"><span data-stu-id="a5489-130">event.</span></span>  
  
6. <xref:System.Windows.Forms.Control.DoubleClick> <span data-ttu-id="a5489-131">.</span><span class="sxs-lookup"><span data-stu-id="a5489-131">event.</span></span> <span data-ttu-id="a5489-132">(Может изменяться в зависимости от того, установлено ли для бита стиля <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> элемента управления значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a5489-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="a5489-133">Подробнее о настройке бита <xref:System.Windows.Forms.ControlStyles> см. в разделе, посвященном методу <xref:System.Windows.Forms.Control.SetStyle%2A>.)</span><span class="sxs-lookup"><span data-stu-id="a5489-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>  
  
7. <xref:System.Windows.Forms.Control.MouseDoubleClick> <span data-ttu-id="a5489-134">.</span><span class="sxs-lookup"><span data-stu-id="a5489-134">event.</span></span>  
  
8. <xref:System.Windows.Forms.Control.MouseUp> <span data-ttu-id="a5489-135">.</span><span class="sxs-lookup"><span data-stu-id="a5489-135">event.</span></span>  
  
 <span data-ttu-id="a5489-136">Пример кода, который демонстрирует порядок мыши события щелчка мыши, см. в разделе [как: Дескриптор пользовательского ввода, события в Windows Forms, элементы управления](how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a5489-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>  
  
### <a name="individual-controls"></a><span data-ttu-id="a5489-137">Особые элементы управления</span><span class="sxs-lookup"><span data-stu-id="a5489-137">Individual Controls</span></span>  
 <span data-ttu-id="a5489-138">Поведение перечисленных ниже элементов управления при щелчке мыши не соответствует стандартному.</span><span class="sxs-lookup"><span data-stu-id="a5489-138">The following controls do not conform to the standard mouse click event behavior:</span></span>  
  
-   <xref:System.Windows.Forms.Button><span data-ttu-id="a5489-139">, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, и <xref:System.Windows.Forms.RadioButton> элементов управления</span><span class="sxs-lookup"><span data-stu-id="a5489-139">, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, and <xref:System.Windows.Forms.RadioButton> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5489-140">Если пользователь щелкает поле редактирования, кнопку или элемент в списке, то для элемента управления <xref:System.Windows.Forms.ComboBox> возникают описанные ниже события.</span><span class="sxs-lookup"><span data-stu-id="a5489-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>  
  
    -   <span data-ttu-id="a5489-141">Щелчок левой кнопкой: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-141">Left click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-142">Щелкните правой кнопкой мыши: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="a5489-142">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="a5489-143">Двойной щелчок левой: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-144">Дважды щелкните справа: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="a5489-144">Right double-click: No click events raised</span></span>  
  
-   <xref:System.Windows.Forms.TextBox><span data-ttu-id="a5489-145">, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, и <xref:System.Windows.Forms.CheckedListBox> элементов управления</span><span class="sxs-lookup"><span data-stu-id="a5489-145">, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5489-146">Если пользователь щелкает любое место внутри этих элементов управления, то возникают описанные ниже события.</span><span class="sxs-lookup"><span data-stu-id="a5489-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>  
  
    -   <span data-ttu-id="a5489-147">Щелчок левой кнопкой: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-147">Left click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-148">Щелкните правой кнопкой мыши: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="a5489-148">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="a5489-149">Двойной щелчок левой: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>,</span><span class="sxs-lookup"><span data-stu-id="a5489-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>,</span></span> <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   <span data-ttu-id="a5489-150">Дважды щелкните справа: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="a5489-150">Right double-click: No click events raised</span></span>  
  
-   <xref:System.Windows.Forms.ListView> <span data-ttu-id="a5489-151">элемент управления</span><span class="sxs-lookup"><span data-stu-id="a5489-151">control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5489-152">Указанные ниже события возникают только в том случае, если пользователь щелкает элементы в <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="a5489-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="a5489-153">Если пользователь щелкает мышью в любом другом месте элемента управления, то события не вызываются.</span><span class="sxs-lookup"><span data-stu-id="a5489-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="a5489-154">В дополнение к событиям, описанным ниже, существуют события <xref:System.Windows.Forms.ListView.BeforeLabelEdit> и <xref:System.Windows.Forms.ListView.AfterLabelEdit>, которые могут представлять интерес, если нужно выполнять проверку с помощью элемента управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="a5489-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    -   <span data-ttu-id="a5489-155">Щелчок левой кнопкой: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-155">Left click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-156">Щелкните правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-156">Right click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-157">Двойной щелчок левой: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span><span class="sxs-lookup"><span data-stu-id="a5489-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span></span> <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   <span data-ttu-id="a5489-158">Справа дважды щелкните: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span><span class="sxs-lookup"><span data-stu-id="a5489-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span></span> <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
-   <xref:System.Windows.Forms.TreeView> <span data-ttu-id="a5489-159">элемент управления</span><span class="sxs-lookup"><span data-stu-id="a5489-159">control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5489-160">Указанные ниже события возникают только в том случае, если пользователь щелкает сами элементы или справа от них в элементе управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="a5489-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="a5489-161">Если пользователь щелкает мышью в любом другом месте элемента управления, то события не вызываются.</span><span class="sxs-lookup"><span data-stu-id="a5489-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="a5489-162">В дополнение к событиям, описанным ниже, существуют события <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> и <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, которые могут представлять интерес, если нужно выполнять проверку с помощью элемента управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="a5489-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
    -   <span data-ttu-id="a5489-163">Щелчок левой кнопкой: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-163">Left click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-164">Щелкните правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>,</span><span class="sxs-lookup"><span data-stu-id="a5489-164">Right click: <xref:System.Windows.Forms.Control.Click>,</span></span> <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   <span data-ttu-id="a5489-165">Двойной щелчок левой: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span><span class="sxs-lookup"><span data-stu-id="a5489-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span></span> <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   <span data-ttu-id="a5489-166">Справа дважды щелкните: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span><span class="sxs-lookup"><span data-stu-id="a5489-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>,</span></span> <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="a5489-167">Поведение отрисовки для переключателей</span><span class="sxs-lookup"><span data-stu-id="a5489-167">Painting Behavior of Toggle Controls</span></span>  
 <span data-ttu-id="a5489-168">Переключатели, такие как элементы управления, производные от класса <xref:System.Windows.Forms.ButtonBase>, имеют описанное ниже нестандартное поведение отрисовки в сочетании с событиями щелчка.</span><span class="sxs-lookup"><span data-stu-id="a5489-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>  
  
1. <span data-ttu-id="a5489-169">Пользователь нажимает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-169">The user presses the mouse button.</span></span>  
  
2. <span data-ttu-id="a5489-170">Элемент управления отрисовывается в состоянии "нажато".</span><span class="sxs-lookup"><span data-stu-id="a5489-170">The control paints in the pressed state.</span></span>  
  
3. <span data-ttu-id="a5489-171">Возникает событие <xref:System.Windows.Forms.Control.MouseDown>.</span><span class="sxs-lookup"><span data-stu-id="a5489-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>  
  
4. <span data-ttu-id="a5489-172">Пользователь отпускает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="a5489-172">The user releases the mouse button.</span></span>  
  
5. <span data-ttu-id="a5489-173">Элемент управления отрисовывается в состоянии "отпущено".</span><span class="sxs-lookup"><span data-stu-id="a5489-173">The control paints in the raised state.</span></span>  
  
6. <span data-ttu-id="a5489-174">Возникает событие <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="a5489-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>  
  
7. <span data-ttu-id="a5489-175">Возникает событие <xref:System.Windows.Forms.Control.MouseClick>.</span><span class="sxs-lookup"><span data-stu-id="a5489-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>  
  
8. <span data-ttu-id="a5489-176">Возникает событие <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="a5489-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5489-177">Если пользователь перемещает указатель за границы переключателя при нажатой кнопке мыши (например, перемещает указатель мыши за границы элемента управления <xref:System.Windows.Forms.Button>, когда он нажат), переключатель будет отрисовываться в состоянии "отпущено" и происходит только событие <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="a5489-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="a5489-178">События <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.MouseClick> в этой ситуации не наступают.</span><span class="sxs-lookup"><span data-stu-id="a5489-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5489-179">См. также</span><span class="sxs-lookup"><span data-stu-id="a5489-179">See also</span></span>

- [<span data-ttu-id="a5489-180">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5489-180">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
