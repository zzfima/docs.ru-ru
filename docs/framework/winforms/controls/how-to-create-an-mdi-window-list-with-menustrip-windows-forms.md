---
title: Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299648"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="65440-102">Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="65440-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="65440-103">Используйте многодокументного интерфейса (MDI) для создания приложений, которые могут открывать несколько документов, в том же время и скопируйте и вставьте содержимое из одного документа в другой.</span><span class="sxs-lookup"><span data-stu-id="65440-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="65440-104">Эта процедура показано, как создать список всех активных дочерних форм в меню родительского окна.</span><span class="sxs-lookup"><span data-stu-id="65440-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="65440-105">Чтобы создать список окна интерфейса MDI в элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="65440-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="65440-106">Создайте форму и присвойте ее свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="65440-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="65440-107">Добавьте на форму элемент <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="65440-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="65440-108">Добавьте два элемента меню верхнего уровня для <xref:System.Windows.Forms.MenuStrip> и задайте их <xref:System.Windows.Forms.Control.Text%2A> свойства `&File` и `&Window`.</span><span class="sxs-lookup"><span data-stu-id="65440-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="65440-109">Добавьте пункт подменю в элемент меню `&File` и присвойте его свойству <xref:System.Windows.Forms.ToolStripItem.Text%2A> значение `&Open`.</span><span class="sxs-lookup"><span data-stu-id="65440-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="65440-110">Задайте <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойство <xref:System.Windows.Forms.MenuStrip> для `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="65440-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="65440-111">Добавьте форму в проект и добавьте нужный элемент управления, такие как другой <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="65440-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="65440-112">Создайте обработчик событий для <xref:System.Windows.Forms.Control.Click> событие `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="65440-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="65440-113">В обработчик событий вставьте код, аналогичный приведенному ниже, чтобы создать и отобразить новые экземпляры `Form2` качестве дочерних окон MDI `Form1`.</span><span class="sxs-lookup"><span data-stu-id="65440-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="65440-114">Поместите код, аналогичный следующему в `&New`<xref:System.Windows.Forms.ToolStripMenuItem> для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="65440-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65440-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="65440-115">Compiling the Code</span></span>  
 <span data-ttu-id="65440-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="65440-116">This example requires:</span></span>  
  
-   <span data-ttu-id="65440-117">два элемента управления <xref:System.Windows.Forms.Form> с именами `Form1` и `Form2`;</span><span class="sxs-lookup"><span data-stu-id="65440-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="65440-118">элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form1` с именем `menuStrip1` и элемент управления <xref:System.Windows.Forms.MenuStrip> на `Form2` с именем `menuStrip2`;</span><span class="sxs-lookup"><span data-stu-id="65440-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="65440-119">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65440-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65440-120">См. также</span><span class="sxs-lookup"><span data-stu-id="65440-120">See also</span></span>

- [<span data-ttu-id="65440-121">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="65440-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="65440-122">Практическое руководство. Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="65440-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="65440-123">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="65440-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
