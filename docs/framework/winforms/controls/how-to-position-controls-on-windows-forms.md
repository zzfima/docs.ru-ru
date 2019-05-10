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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211654"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="8c864-102">Практическое руководство. Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-102">How to: Position Controls on Windows Forms</span></span>

<span data-ttu-id="8c864-103">Размещение элементов управления, использовать конструктор Windows Forms в Visual Studio или задайте <xref:System.Windows.Forms.Control.Location%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c864-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="8c864-104">Разместить элемент управления в области конструктора в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="8c864-105">В Visual Studio перетащите элемент управления в соответствующее место с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="8c864-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="8c864-106">Выберите элемент управления и переместите его с помощью стрелки клавиш со стрелками для более точно.</span><span class="sxs-lookup"><span data-stu-id="8c864-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="8c864-107">Кроме того *линии привязки* помочь для точного размещения.</span><span class="sxs-lookup"><span data-stu-id="8c864-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="8c864-108">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочение элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="8c864-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="8c864-109">Положение элемента управления, с помощью окна свойств</span><span class="sxs-lookup"><span data-stu-id="8c864-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="8c864-110">В Visual Studio щелкните элемент управления, который можно разместить.</span><span class="sxs-lookup"><span data-stu-id="8c864-110">In Visual Studio, click the control you want to position.</span></span>

2. <span data-ttu-id="8c864-111">В **свойства** окне значения типов <xref:System.Windows.Forms.Control.Location%2A> свойств, разделенных запятыми, чтобы разместить элемент управления внутри контейнера.</span><span class="sxs-lookup"><span data-stu-id="8c864-111">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

     <span data-ttu-id="8c864-112">Первое число (X) является расстоянием от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряется в пикселах.</span><span class="sxs-lookup"><span data-stu-id="8c864-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c864-113">Вы можете развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство в тип **X** и **Y** отдельно.</span><span class="sxs-lookup"><span data-stu-id="8c864-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="8c864-114">Поместите элемент управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="8c864-114">Position a control programmatically</span></span>

1. <span data-ttu-id="8c864-115">Задайте <xref:System.Windows.Forms.Control.Location%2A> свойство элемента управления, <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="8c864-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="8c864-116">Измените значение координаты X местоположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> подсвойства.</span><span class="sxs-lookup"><span data-stu-id="8c864-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="8c864-117">Увеличить расположение элемента управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="8c864-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="8c864-118">Задайте <xref:System.Windows.Forms.Control.Left%2A> подсвойств координату X элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8c864-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="8c864-119">Используйте <xref:System.Windows.Forms.Control.Location%2A> одновременно помещает свойства X и Y элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8c864-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="8c864-120">Чтобы задать положение по отдельности, используйте элемент управления <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) подсвойства.</span><span class="sxs-lookup"><span data-stu-id="8c864-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="8c864-121">Не пытайтесь неявным образом значение координаты X и Y <xref:System.Drawing.Point> структура, представляющая расположение кнопки, так как эта структура содержит копию координат кнопки.</span><span class="sxs-lookup"><span data-stu-id="8c864-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c864-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8c864-122">See also</span></span>

- [<span data-ttu-id="8c864-123">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="8c864-124">Пошаговое руководство: Упорядочение элементов управления в формах Windows Forms, с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="8c864-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="8c864-125">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8c864-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="8c864-126">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8c864-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="8c864-127">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-127">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="8c864-128">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="8c864-129">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="8c864-130">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c864-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="8c864-131">[Практическое руководство. Задание расположения экрана Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8c864-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
