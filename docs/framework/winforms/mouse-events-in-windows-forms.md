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
ms.openlocfilehash: 818364ceddb03df51ed656c8ff7b69fd433ac86a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750895"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="ffbdf-102">События мыши в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffbdf-102">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="ffbdf-103">При обработке ввода данных с помощью мыши обычно необходимо знать положение указателя и состояние кнопок мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="ffbdf-104">В этом разделе приводится подробная информация о получении этих сведений из событий мыши и описывается порядок, в котором вызываются события щелчка мыши в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="ffbdf-105">Список и описание всех событий мыши, см. в разделе [принцип работы мыши ввода в Windows Forms](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ffbdf-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="ffbdf-106">Также см. в разделе [Обзор обработчиков событий (Windows Forms)](event-handlers-overview-windows-forms.md) и [Общие сведения о событиях (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ffbdf-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="ffbdf-107">Сведения о мыши</span><span class="sxs-lookup"><span data-stu-id="ffbdf-107">Mouse Information</span></span>

<span data-ttu-id="ffbdf-108">Объект <xref:System.Windows.Forms.MouseEventArgs> отправляется обработчикам событий мыши, связанных с нажатием кнопки мыши и отслеживанием ее движений.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="ffbdf-109">Объект <xref:System.Windows.Forms.MouseEventArgs> предоставляет сведения о текущем состоянии мыши, включая положение указателя мыши в клиентских координатах, какие кнопки мыши нажаты и произошла ли прокрутка колесика мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="ffbdf-110">Некоторые события мыши, например те, которые просто уведомляют о том, что указатель мыши пересек границы элемента управления, отправляют обработчику событий объект <xref:System.EventArgs> без подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="ffbdf-111">Если нужно знать текущее состояние кнопок мыши или положение ее указателя, но при этом избежать обработки события мыши, можно также использовать свойства <xref:System.Windows.Forms.Control.MouseButtons%2A> и <xref:System.Windows.Forms.Control.MousePosition%2A> класса <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="ffbdf-112">Свойство <xref:System.Windows.Forms.Control.MouseButtons%2A> возвращает сведения о том, какие кнопки мыши в настоящее время нажаты.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="ffbdf-113">Свойство <xref:System.Windows.Forms.Control.MousePosition%2A> возвращает экранные координаты указателя мыши, которые эквивалентны значению, возвращаемому методом <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="ffbdf-114">Преобразование между экранными и клиентскими координатами</span><span class="sxs-lookup"><span data-stu-id="ffbdf-114">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="ffbdf-115">Так как некоторые сведения о положении мыши представлены в клиентских координатах, а другие — в экранных, может потребоваться преобразовать точку из одной системы координат в другую.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="ffbdf-116">Это легко сделать с помощью методов <xref:System.Windows.Forms.Control.PointToClient%2A> и <xref:System.Windows.Forms.Control.PointToScreen%2A>, доступных в классе <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="ffbdf-117">Стандартное поведение события щелчка</span><span class="sxs-lookup"><span data-stu-id="ffbdf-117">Standard Click Event Behavior</span></span>

<span data-ttu-id="ffbdf-118">Если требуется обрабатывать события щелчка мыши в определенном порядке, необходимо знать порядок, в котором вызываются события щелчка в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="ffbdf-119">Когда кнопка мыши (любая) нажимается и отпускается, все элементы управления Windows Forms, кроме отмеченных в списке ниже, вызывают события щелчка в одном и том же порядке.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="ffbdf-120">Ниже приведен порядок событий, вызываемых одинарным щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-120">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="ffbdf-121">Событие<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="ffbdf-122">Событие<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="ffbdf-123">Событие<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="ffbdf-124">Событие<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="ffbdf-125">Ниже приведен порядок событий, вызываемых двойным щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-125">Following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="ffbdf-126">Событие<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="ffbdf-127">Событие<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="ffbdf-128">Событие<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="ffbdf-129">Событие<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="ffbdf-130">Событие<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="ffbdf-131">Событие<xref:System.Windows.Forms.Control.DoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="ffbdf-132">(Может изменяться в зависимости от того, установлено ли для бита стиля <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> элемента управления значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="ffbdf-133">Подробнее о настройке бита <xref:System.Windows.Forms.ControlStyles> см. в разделе, посвященном методу <xref:System.Windows.Forms.Control.SetStyle%2A>.)</span><span class="sxs-lookup"><span data-stu-id="ffbdf-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="ffbdf-134">Событие<xref:System.Windows.Forms.Control.MouseDoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="ffbdf-135">Событие<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="ffbdf-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="ffbdf-136">Пример кода, который демонстрирует порядок мыши события щелчка мыши, см. в разделе [как: Дескриптор пользовательского ввода, события в Windows Forms, элементы управления](how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ffbdf-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="ffbdf-137">Особые элементы управления</span><span class="sxs-lookup"><span data-stu-id="ffbdf-137">Individual Controls</span></span>

<span data-ttu-id="ffbdf-138">Поведение перечисленных ниже элементов управления при щелчке мыши не соответствует стандартному.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-138">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <span data-ttu-id="ffbdf-139">Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.RadioButton></span><span class="sxs-lookup"><span data-stu-id="ffbdf-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, and <xref:System.Windows.Forms.RadioButton> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffbdf-140">Если пользователь щелкает поле редактирования, кнопку или элемент в списке, то для элемента управления <xref:System.Windows.Forms.ComboBox> возникают описанные ниже события.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="ffbdf-141">Щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-141">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-142">Щелкните правой кнопкой мыши: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="ffbdf-142">Right click: No click events raised</span></span>

  - <span data-ttu-id="ffbdf-143">Двойной щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-144">Дважды щелкните справа: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="ffbdf-144">Right double-click: No click events raised</span></span>

- <span data-ttu-id="ffbdf-145">Элементы управления <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> и <xref:System.Windows.Forms.CheckedListBox></span><span class="sxs-lookup"><span data-stu-id="ffbdf-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffbdf-146">Если пользователь щелкает любое место внутри этих элементов управления, то возникают описанные ниже события.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="ffbdf-147">Щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-147">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-148">Щелкните правой кнопкой мыши: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="ffbdf-148">Right click: No click events raised</span></span>

  - <span data-ttu-id="ffbdf-149">Двойной щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="ffbdf-150">Дважды щелкните справа: Событие щелчка не вызывается</span><span class="sxs-lookup"><span data-stu-id="ffbdf-150">Right double-click: No click events raised</span></span>

- <span data-ttu-id="ffbdf-151">Элемент управления <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="ffbdf-151"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffbdf-152">Указанные ниже события возникают только в том случае, если пользователь щелкает элементы в <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="ffbdf-153">Если пользователь щелкает мышью в любом другом месте элемента управления, то события не вызываются.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="ffbdf-154">В дополнение к событиям, описанным ниже, существуют события <xref:System.Windows.Forms.ListView.BeforeLabelEdit> и <xref:System.Windows.Forms.ListView.AfterLabelEdit>, которые могут представлять интерес, если нужно выполнять проверку с помощью элемента управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="ffbdf-155">Щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-155">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-156">Щелчок правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-156">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-157">Двойной щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="ffbdf-158">Двойной щелчок правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="ffbdf-159">Элемент управления <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="ffbdf-159"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffbdf-160">Указанные ниже события возникают только в том случае, если пользователь щелкает сами элементы или справа от них в элементе управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="ffbdf-161">Если пользователь щелкает мышью в любом другом месте элемента управления, то события не вызываются.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="ffbdf-162">В дополнение к событиям, описанным ниже, существуют события <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> и <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, которые могут представлять интерес, если нужно выполнять проверку с помощью элемента управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="ffbdf-163">Щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-163">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-164">Щелчок правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-164">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="ffbdf-165">Двойной щелчок левой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="ffbdf-166">Двойной щелчок правой кнопкой мыши: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="ffbdf-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="ffbdf-167">Поведение отрисовки для переключателей</span><span class="sxs-lookup"><span data-stu-id="ffbdf-167">Painting Behavior of Toggle Controls</span></span>

<span data-ttu-id="ffbdf-168">Переключатели, такие как элементы управления, производные от класса <xref:System.Windows.Forms.ButtonBase>, имеют описанное ниже нестандартное поведение отрисовки в сочетании с событиями щелчка.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="ffbdf-169">Пользователь нажимает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-169">The user presses the mouse button.</span></span>

2. <span data-ttu-id="ffbdf-170">Элемент управления отрисовывается в состоянии "нажато".</span><span class="sxs-lookup"><span data-stu-id="ffbdf-170">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="ffbdf-171">Возникает событие <xref:System.Windows.Forms.Control.MouseDown>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="ffbdf-172">Пользователь отпускает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-172">The user releases the mouse button.</span></span>

5. <span data-ttu-id="ffbdf-173">Элемент управления отрисовывается в состоянии "отпущено".</span><span class="sxs-lookup"><span data-stu-id="ffbdf-173">The control paints in the raised state.</span></span>

6. <span data-ttu-id="ffbdf-174">Возникает событие <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="ffbdf-175">Возникает событие <xref:System.Windows.Forms.Control.MouseClick>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="ffbdf-176">Возникает событие <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="ffbdf-177">Если пользователь перемещает указатель за границы переключателя при нажатой кнопке мыши (например, перемещает указатель мыши за границы элемента управления <xref:System.Windows.Forms.Button>, когда он нажат), переключатель будет отрисовываться в состоянии "отпущено" и происходит только событие <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="ffbdf-178">События <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.MouseClick> в этой ситуации не наступают.</span><span class="sxs-lookup"><span data-stu-id="ffbdf-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffbdf-179">См. также</span><span class="sxs-lookup"><span data-stu-id="ffbdf-179">See also</span></span>

- [<span data-ttu-id="ffbdf-180">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffbdf-180">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
