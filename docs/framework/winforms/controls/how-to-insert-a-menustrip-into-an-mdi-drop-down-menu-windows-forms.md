---
title: Практическое руководство. Вставка элемента MenuStrip в раскрывающемся меню интерфейса MDI (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 1b41699d8da1c99705f6796105dab6f3ab1d727d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941119"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="cad59-102">Практическое руководство. Вставка элемента MenuStrip в раскрывающемся меню интерфейса MDI (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cad59-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="cad59-103">В некоторых приложениях вид дочернего окна многодокументного интерфейса (MDI) может отличаться от родительского окна MDI.</span><span class="sxs-lookup"><span data-stu-id="cad59-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="cad59-104">Например, родительским окном MDI может быть электронная таблица, а дочерним окном MDI — диаграмма.</span><span class="sxs-lookup"><span data-stu-id="cad59-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="cad59-105">В этом случае может потребоваться дополнить содержимое меню родительского окна MDI содержимым меню дочерней MDI-формы, по мере того как активируются дочерние окна MDI различных типов.</span><span class="sxs-lookup"><span data-stu-id="cad59-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="cad59-106">В следующей процедуре используется <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> свойства, чтобы вставить группу пунктов меню из дочернего меню MDI в в раскрывающегося списка части родительского меню MDI.</span><span class="sxs-lookup"><span data-stu-id="cad59-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="cad59-107">При закрытии дочернего окна MDI удаляются пункты меню, вставленные из родительского окна MDI.</span><span class="sxs-lookup"><span data-stu-id="cad59-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="cad59-108">Чтобы Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI</span><span class="sxs-lookup"><span data-stu-id="cad59-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="cad59-109">Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cad59-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="cad59-110">Добавьте <xref:System.Windows.Forms.MenuStrip> на `Form1` и присвойте свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> для элемента <xref:System.Windows.Forms.MenuStrip> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cad59-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="cad59-111">Добавьте пункт меню верхнего уровня в `Form1`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.Control.Text%2A> значение `&File`.</span><span class="sxs-lookup"><span data-stu-id="cad59-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="cad59-112">Добавьте три элемента вложенного меню для `&File` пункта меню и задайте их <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства `&Open`, `&Import from`, и `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="cad59-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="cad59-113">Добавьте два подменю к `&Import from` подменю и задайте их <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства `&Word` и `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="cad59-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="cad59-114">Добавьте в проект форму, добавьте <xref:System.Windows.Forms.MenuStrip> на форму и присвойте его свойству <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> элемента `Form2`<xref:System.Windows.Forms.MenuStrip> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cad59-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="cad59-115">Добавьте пункт меню верхнего уровня в `Form2`<xref:System.Windows.Forms.MenuStrip> и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&File`.</span><span class="sxs-lookup"><span data-stu-id="cad59-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="cad59-116">Добавить подменю `&File` меню `Form2` в следующем порядке: <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`и другой <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="cad59-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="cad59-117">Задайте <xref:System.Windows.Forms.MergeAction> и <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> свойства `Form2` пункты меню, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cad59-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="cad59-118">Пункт меню Form2</span><span class="sxs-lookup"><span data-stu-id="cad59-118">Form2 menu item</span></span>|<span data-ttu-id="cad59-119">Значение MergeAction</span><span class="sxs-lookup"><span data-stu-id="cad59-119">MergeAction value</span></span>|<span data-ttu-id="cad59-120">Значение MergeIndex</span><span class="sxs-lookup"><span data-stu-id="cad59-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="cad59-121">Файл</span><span class="sxs-lookup"><span data-stu-id="cad59-121">File</span></span>|<span data-ttu-id="cad59-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="cad59-122">MatchOnly</span></span>|<span data-ttu-id="cad59-123">-1</span><span class="sxs-lookup"><span data-stu-id="cad59-123">-1</span></span>|  
    |<span data-ttu-id="cad59-124">Separator</span><span class="sxs-lookup"><span data-stu-id="cad59-124">Separator</span></span>|<span data-ttu-id="cad59-125">Insert</span><span class="sxs-lookup"><span data-stu-id="cad59-125">Insert</span></span>|<span data-ttu-id="cad59-126">2</span><span class="sxs-lookup"><span data-stu-id="cad59-126">2</span></span>|  
    |<span data-ttu-id="cad59-127">Сохранение</span><span class="sxs-lookup"><span data-stu-id="cad59-127">Save</span></span>|<span data-ttu-id="cad59-128">Insert</span><span class="sxs-lookup"><span data-stu-id="cad59-128">Insert</span></span>|<span data-ttu-id="cad59-129">3</span><span class="sxs-lookup"><span data-stu-id="cad59-129">3</span></span>|  
    |<span data-ttu-id="cad59-130">Сохранить и закрыть</span><span class="sxs-lookup"><span data-stu-id="cad59-130">Save and Close</span></span>|<span data-ttu-id="cad59-131">Insert</span><span class="sxs-lookup"><span data-stu-id="cad59-131">Insert</span></span>|<span data-ttu-id="cad59-132">4</span><span class="sxs-lookup"><span data-stu-id="cad59-132">4</span></span>|  
    |<span data-ttu-id="cad59-133">Separator</span><span class="sxs-lookup"><span data-stu-id="cad59-133">Separator</span></span>|<span data-ttu-id="cad59-134">Insert</span><span class="sxs-lookup"><span data-stu-id="cad59-134">Insert</span></span>|<span data-ttu-id="cad59-135">5</span><span class="sxs-lookup"><span data-stu-id="cad59-135">5</span></span>|  
  
10. <span data-ttu-id="cad59-136">Создайте обработчик событий для события <xref:System.Windows.Forms.Control.Click> элемента `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="cad59-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="cad59-137">В обработчик событий вставьте код, аналогичный приведенному в следующем примере для создания и отображения новых экземпляров `Form2` в качестве дочерних окон MDI `Form1`.</span><span class="sxs-lookup"><span data-stu-id="cad59-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
12. <span data-ttu-id="cad59-138">Поместите код, аналогичный приведенному в следующем примере, в `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>, для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="cad59-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cad59-139">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cad59-139">Compiling the Code</span></span>  
 <span data-ttu-id="cad59-140">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="cad59-140">This example requires:</span></span>  
  
- <span data-ttu-id="cad59-141">два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;</span><span class="sxs-lookup"><span data-stu-id="cad59-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="cad59-142">элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;</span><span class="sxs-lookup"><span data-stu-id="cad59-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="cad59-143">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cad59-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad59-144">См. также</span><span class="sxs-lookup"><span data-stu-id="cad59-144">See also</span></span>

- [<span data-ttu-id="cad59-145">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="cad59-145">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="cad59-146">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="cad59-146">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="cad59-147">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="cad59-147">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
