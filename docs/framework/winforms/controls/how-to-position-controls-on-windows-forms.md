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
ms.openlocfilehash: 6db021f2b1a29c3ef52a182c45bbc7878feebb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538716"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="7ac3c-102">Практическое руководство. Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="7ac3c-103">Размещение элементов управления, использовать конструктор Windows Forms или задайте <xref:System.Windows.Forms.Control.Location%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ac3c-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7ac3c-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="7ac3c-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7ac3c-106">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="7ac3c-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="7ac3c-107">Чтобы разместить элемент управления в рабочей области конструирования в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="7ac3c-108">Перетащите элемент управления в нужное место с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac3c-109">Выберите элемент управления и переместите его со стрелкой клавиш со стрелками для более точного.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="7ac3c-110">Кроме того *линии привязки* поможет для точного размещения.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="7ac3c-111">Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="7ac3c-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="7ac3c-112">Чтобы разместить элемент управления с помощью окна свойств</span><span class="sxs-lookup"><span data-stu-id="7ac3c-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="7ac3c-113">Щелкните элемент управления, который можно разместить.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="7ac3c-114">В **свойства** окна, тип значения для <xref:System.Windows.Forms.Control.Location%2A> свойств, разделенных запятыми, чтобы разместить элемент управления внутри контейнера.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="7ac3c-115">Первое число (X) представляет собой расстояние от левой границы контейнера; второе число (Y) представляет собой расстояние от верхней границы области контейнера, измеряется в пикселях.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ac3c-116">Вы можете развернуть <xref:System.Windows.Forms.Control.Location%2A> свойство в тип **X** и **Y** отдельно.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="7ac3c-117">Чтобы разместить элемент управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="7ac3c-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="7ac3c-118">Задать <xref:System.Windows.Forms.Control.Location%2A> свойства элемента управления для <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="7ac3c-119">Измените значение координаты X местоположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> вложенное свойство.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="7ac3c-120">Чтобы увеличить расположение элемента управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="7ac3c-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="7ac3c-121">Задать <xref:System.Windows.Forms.Control.Left%2A> подчиненное координату X элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
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
    >  <span data-ttu-id="7ac3c-122">Используйте <xref:System.Windows.Forms.Control.Location%2A> одновременно помещает свойства X и Y элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="7ac3c-123">Чтобы задать положение по отдельности, используйте элемент управления <xref:System.Windows.Forms.Control.Left%2A> (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) вложенное свойство.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="7ac3c-124">Не пытайтесь неявно задать координаты X и Y <xref:System.Drawing.Point> структуру, которая представляет расположение кнопки, потому что эта структура содержит копию координат кнопки.</span><span class="sxs-lookup"><span data-stu-id="7ac3c-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac3c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7ac3c-125">See Also</span></span>  
 [<span data-ttu-id="7ac3c-126">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="7ac3c-127">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="7ac3c-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="7ac3c-128">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7ac3c-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="7ac3c-129">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7ac3c-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="7ac3c-130">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="7ac3c-131">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="7ac3c-132">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="7ac3c-133">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="7ac3c-134">Как: задать расположение экрана формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ac3c-134">How to: Set the Screen Location of Windows Forms</span></span>](http://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
