---
title: Практическое руководство. Размещение элементов управления в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: a0b97073b2f9363a64bfc4a4ede7ffa69e2bce42
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334007"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="67b33-102">Практическое руководство. Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="67b33-103">Размещение элементов управления, использовать конструктор Windows Forms или задайте <xref:System.Windows.Forms.Control.Location%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="67b33-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67b33-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="67b33-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="67b33-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="67b33-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="67b33-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="67b33-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="67b33-107">Чтобы разместить элемент управления в области конструктора в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="67b33-108">Перетащите элемент управления в соответствующее место с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="67b33-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67b33-109">Выберите элемент управления и переместите его с помощью стрелки клавиш со стрелками для более точно.</span><span class="sxs-lookup"><span data-stu-id="67b33-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="67b33-110">Кроме того *линии привязки* помочь для точного размещения.</span><span class="sxs-lookup"><span data-stu-id="67b33-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="67b33-111">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочение элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="67b33-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="67b33-112">Чтобы разместить элемент управления, с помощью окна свойств</span><span class="sxs-lookup"><span data-stu-id="67b33-112">To position a control using the Properties window</span></span>  
  
1. <span data-ttu-id="67b33-113">Щелкните элемент управления, который можно разместить.</span><span class="sxs-lookup"><span data-stu-id="67b33-113">Click the control you want to position.</span></span>  
  
2. <span data-ttu-id="67b33-114">В **свойства** окне значения типов <xref:System.Windows.Forms.Control.Location%2A> свойств, разделенных запятыми, чтобы разместить элемент управления внутри контейнера.</span><span class="sxs-lookup"><span data-stu-id="67b33-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="67b33-115">Первое число (X) является расстоянием от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряется в пикселах.</span><span class="sxs-lookup"><span data-stu-id="67b33-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67b33-116">Вы можете развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство в тип **X** и **Y** отдельно.</span><span class="sxs-lookup"><span data-stu-id="67b33-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="67b33-117">Чтобы разместить элемент управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="67b33-117">To position a control programmatically</span></span>  
  
1. <span data-ttu-id="67b33-118">Задайте <xref:System.Windows.Forms.Control.Location%2A> свойство элемента управления, <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="67b33-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2. <span data-ttu-id="67b33-119">Измените значение координаты X местоположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> подсвойства.</span><span class="sxs-lookup"><span data-stu-id="67b33-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="67b33-120">Увеличиваемый расположение элемента управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="67b33-120">To increment a control's location programmatically</span></span>  
  
1. <span data-ttu-id="67b33-121">Задайте <xref:System.Windows.Forms.Control.Left%2A> подсвойств координату X элемента управления.</span><span class="sxs-lookup"><span data-stu-id="67b33-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="67b33-122">Используйте <xref:System.Windows.Forms.Control.Location%2A> одновременно помещает свойства X и Y элемента управления.</span><span class="sxs-lookup"><span data-stu-id="67b33-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="67b33-123">Чтобы задать положение по отдельности, используйте элемент управления <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) подсвойства.</span><span class="sxs-lookup"><span data-stu-id="67b33-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="67b33-124">Не пытайтесь неявным образом значение координаты X и Y <xref:System.Drawing.Point> структура, представляющая расположение кнопки, так как эта структура содержит копию координат кнопки.</span><span class="sxs-lookup"><span data-stu-id="67b33-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b33-125">См. также</span><span class="sxs-lookup"><span data-stu-id="67b33-125">See also</span></span>

- [<span data-ttu-id="67b33-126">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-126">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="67b33-127">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="67b33-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="67b33-128">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="67b33-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="67b33-129">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="67b33-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="67b33-130">Расположение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-130">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="67b33-131">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="67b33-132">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="67b33-133">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-133">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="67b33-134">Практическое руководство. Задание расположения экрана Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67b33-134">How to: Set the Screen Location of Windows Forms</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
