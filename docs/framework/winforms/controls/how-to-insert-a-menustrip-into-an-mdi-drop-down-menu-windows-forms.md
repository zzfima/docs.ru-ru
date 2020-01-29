---
title: Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736404"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="934e4-102">Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="934e4-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="934e4-103">В некоторых приложениях вид дочернего окна многодокументного интерфейса (MDI) может отличаться от родительского окна MDI.</span><span class="sxs-lookup"><span data-stu-id="934e4-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="934e4-104">Например, родительским окном MDI может быть электронная таблица, а дочерним окном MDI — диаграмма.</span><span class="sxs-lookup"><span data-stu-id="934e4-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="934e4-105">В этом случае может потребоваться дополнить содержимое меню родительского окна MDI содержимым меню дочерней MDI-формы, по мере того как активируются дочерние окна MDI различных типов.</span><span class="sxs-lookup"><span data-stu-id="934e4-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="934e4-106">В следующей процедуре используются свойства <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> для вставки группы пунктов меню из дочернего меню MDI в раскрывающийся список родительского меню MDI.</span><span class="sxs-lookup"><span data-stu-id="934e4-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="934e4-107">При закрытии дочернего окна MDI элементы вставленного меню удаляются из родительского интерфейса MDI.</span><span class="sxs-lookup"><span data-stu-id="934e4-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="934e4-108">Вставка объекта MenuStrip в раскрывающееся меню MDI</span><span class="sxs-lookup"><span data-stu-id="934e4-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="934e4-109">Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="934e4-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="934e4-110">Добавьте <xref:System.Windows.Forms.MenuStrip> на `Form1` и присвойте свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> для элемента <xref:System.Windows.Forms.MenuStrip> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="934e4-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="934e4-111">Добавьте пункт меню верхнего уровня в `Form1`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.Control.Text%2A> значение `&File`.</span><span class="sxs-lookup"><span data-stu-id="934e4-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="934e4-112">Добавьте три пункта подменю в элемент меню `&File` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`, `&Import from`и `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="934e4-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="934e4-113">Добавьте два пункта подменю в элемент вложенного меню `&Import from` и задайте для свойств <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Word` и `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="934e4-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="934e4-114">Добавьте в проект форму, добавьте <xref:System.Windows.Forms.MenuStrip> на форму и присвойте его свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> элемента `Form2`<xref:System.Windows.Forms.MenuStrip> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="934e4-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="934e4-115">Добавьте пункт меню верхнего уровня в `Form2`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&File`.</span><span class="sxs-lookup"><span data-stu-id="934e4-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="934e4-116">Добавьте элементы подменю в меню `&File` `Form2` в следующем порядке: <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`и другой <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="934e4-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="934e4-117">Задайте свойства <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> пунктов меню `Form2`, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="934e4-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="934e4-118">Пункт меню Form2</span><span class="sxs-lookup"><span data-stu-id="934e4-118">Form2 menu item</span></span>|<span data-ttu-id="934e4-119">Значение Мержеактион</span><span class="sxs-lookup"><span data-stu-id="934e4-119">MergeAction value</span></span>|<span data-ttu-id="934e4-120">Значение Мержеиндекс</span><span class="sxs-lookup"><span data-stu-id="934e4-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="934e4-121">File</span><span class="sxs-lookup"><span data-stu-id="934e4-121">File</span></span>|<span data-ttu-id="934e4-122">матчонли</span><span class="sxs-lookup"><span data-stu-id="934e4-122">MatchOnly</span></span>|<span data-ttu-id="934e4-123">-1</span><span class="sxs-lookup"><span data-stu-id="934e4-123">-1</span></span>|  
    |<span data-ttu-id="934e4-124">Separator</span><span class="sxs-lookup"><span data-stu-id="934e4-124">Separator</span></span>|<span data-ttu-id="934e4-125">Insert</span><span class="sxs-lookup"><span data-stu-id="934e4-125">Insert</span></span>|<span data-ttu-id="934e4-126">2</span><span class="sxs-lookup"><span data-stu-id="934e4-126">2</span></span>|  
    |<span data-ttu-id="934e4-127">Сохранить</span><span class="sxs-lookup"><span data-stu-id="934e4-127">Save</span></span>|<span data-ttu-id="934e4-128">Insert</span><span class="sxs-lookup"><span data-stu-id="934e4-128">Insert</span></span>|<span data-ttu-id="934e4-129">3</span><span class="sxs-lookup"><span data-stu-id="934e4-129">3</span></span>|  
    |<span data-ttu-id="934e4-130">Сохранить и закрыть</span><span class="sxs-lookup"><span data-stu-id="934e4-130">Save and Close</span></span>|<span data-ttu-id="934e4-131">Insert</span><span class="sxs-lookup"><span data-stu-id="934e4-131">Insert</span></span>|<span data-ttu-id="934e4-132">4</span><span class="sxs-lookup"><span data-stu-id="934e4-132">4</span></span>|  
    |<span data-ttu-id="934e4-133">Separator</span><span class="sxs-lookup"><span data-stu-id="934e4-133">Separator</span></span>|<span data-ttu-id="934e4-134">Insert</span><span class="sxs-lookup"><span data-stu-id="934e4-134">Insert</span></span>|<span data-ttu-id="934e4-135">5</span><span class="sxs-lookup"><span data-stu-id="934e4-135">5</span></span>|  
  
10. <span data-ttu-id="934e4-136">Создайте обработчик событий для события <xref:System.Windows.Forms.Control.Click> элемента `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="934e4-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="934e4-137">В обработчик событий вставьте код, аналогичный приведенному в следующем примере для создания и отображения новых экземпляров `Form2` в качестве дочерних окон MDI `Form1`.</span><span class="sxs-lookup"><span data-stu-id="934e4-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="934e4-138">Поместите код, аналогичный приведенному в следующем примере, в `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>, для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="934e4-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="934e4-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="934e4-139">Compiling the Code</span></span>  
 <span data-ttu-id="934e4-140">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="934e4-140">This example requires:</span></span>  
  
- <span data-ttu-id="934e4-141">два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;</span><span class="sxs-lookup"><span data-stu-id="934e4-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="934e4-142">элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;</span><span class="sxs-lookup"><span data-stu-id="934e4-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="934e4-143">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="934e4-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934e4-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="934e4-144">See also</span></span>

- [<span data-ttu-id="934e4-145">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="934e4-145">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="934e4-146">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="934e4-146">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="934e4-147">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="934e4-147">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
