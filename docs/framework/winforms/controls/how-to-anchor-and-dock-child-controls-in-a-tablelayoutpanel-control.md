---
title: Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: a4fcb4e527825a9946861a46dc336db227e52296
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709631"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="b31d1-102">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b31d1-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="b31d1-103">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> поддерживает свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> в своих дочерних элементах управления.</span><span class="sxs-lookup"><span data-stu-id="b31d1-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="b31d1-104">Выравнивание дочернего элемента управления в ячейке TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b31d1-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="b31d1-105">Создание элемента управления <xref:System.Windows.Forms.TableLayoutPanel> в форме.</span><span class="sxs-lookup"><span data-stu-id="b31d1-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2.  <span data-ttu-id="b31d1-106">Установите для параметра <xref:System.Windows.Forms.TableLayoutPanel> элемента управления <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> и <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> свойства **1**.</span><span class="sxs-lookup"><span data-stu-id="b31d1-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3.  <span data-ttu-id="b31d1-107">Создайте элемент управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="b31d1-108">Элемент <xref:System.Windows.Forms.Button> расположен в левом верхнем углу ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4.  <span data-ttu-id="b31d1-109">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Left`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="b31d1-110">Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b31d1-111">Такое поведение отличается от поведения других контейнерных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="b31d1-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="b31d1-112">Когда свойству <xref:System.Windows.Forms.Control.Anchor%2A> присваивается значение<xref:System.Windows.Forms.Control.Anchor%2A>, дочерние элементы управления других контейнерных элементов управления не перемещаются, а расстояние между закрепленным элементом управления и границей родительского контейнера фиксируется.</span><span class="sxs-lookup"><span data-stu-id="b31d1-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5.  <span data-ttu-id="b31d1-113">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="b31d1-114">Элемент управления <xref:System.Windows.Forms.Button> займет левый верхний угол ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6.  <span data-ttu-id="b31d1-115">Повторите шаг 5 со значением из `Top, Right` для перемещения <xref:System.Windows.Forms.Button> элемента управления в правом верхнем углу ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="b31d1-116">Повторите процедуру, используя значения `Bottom, Left` и `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="b31d1-117">Растяжение дочернего элемента управления в ячейке TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b31d1-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="b31d1-118">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="b31d1-119">Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по ширине ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b31d1-120">Такое поведение отличается от поведения других контейнерных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="b31d1-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="b31d1-121">В других контейнерных элементов управления, дочерний элемент управления не изменяются, когда <xref:System.Windows.Forms.Control.Anchor%2A> свойству `Left, Right` или `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2.  <span data-ttu-id="b31d1-122">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="b31d1-123">Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он растянется по высоте ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3.  <span data-ttu-id="b31d1-124">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="b31d1-125">Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.</span><span class="sxs-lookup"><span data-stu-id="b31d1-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4.  <span data-ttu-id="b31d1-126">Измените значение свойства <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> на `None`.</span><span class="sxs-lookup"><span data-stu-id="b31d1-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="b31d1-127">Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он расположится по центру ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5.  <span data-ttu-id="b31d1-128">Измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="b31d1-129">Элемент управления <xref:System.Windows.Forms.Button> выровняется по левому краю ячейки.</span><span class="sxs-lookup"><span data-stu-id="b31d1-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="b31d1-130">Ширина элемента управления <xref:System.Windows.Forms.Button> сохранится, а высота изменится для заполнения ячейки по вертикали.</span><span class="sxs-lookup"><span data-stu-id="b31d1-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b31d1-131">Другие контейнерные элементы управления обладают аналогичным поведением.</span><span class="sxs-lookup"><span data-stu-id="b31d1-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6.  <span data-ttu-id="b31d1-132">Измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="b31d1-133">Размер элемента управления <xref:System.Windows.Forms.Button> изменится, и он заполнит ячейку.</span><span class="sxs-lookup"><span data-stu-id="b31d1-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b31d1-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b31d1-134">Example</span></span>  
 <span data-ttu-id="b31d1-135">На рисунке ниже показаны пять кнопок, прикрепленных в пяти отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="b31d1-136">![Закрепление TableLayoutPanel](./media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="b31d1-136">![TableLayoutPanel Anchoring](./media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="b31d1-137">На рисунке ниже показаны четыре кнопки, прикрепленные в углах четырех отдельных ячеек <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="b31d1-138">![Закрепление TableLayoutPanel](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="b31d1-138">![TableLayoutPanel Anchoring](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="b31d1-139">На рисунке ниже показаны три кнопки, растянутые в результате прикрепления в трех отдельных ячейках <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="b31d1-140">![Закрепление TableLayoutPanel](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="b31d1-140">![TableLayoutPanel Anchoring](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="b31d1-141">В примере кода ниже демонстрируются все сочетания значений свойств <xref:System.Windows.Forms.Control.Anchor%2A>, используемые для размещения элемента управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="b31d1-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b31d1-142">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b31d1-142">Compiling the Code</span></span>  
 <span data-ttu-id="b31d1-143">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b31d1-143">This example requires:</span></span>  
  
-   <span data-ttu-id="b31d1-144">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b31d1-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b31d1-145">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b31d1-145">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b31d1-146">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="b31d1-146">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31d1-147">См. также</span><span class="sxs-lookup"><span data-stu-id="b31d1-147">See also</span></span>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="b31d1-148">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b31d1-148">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
