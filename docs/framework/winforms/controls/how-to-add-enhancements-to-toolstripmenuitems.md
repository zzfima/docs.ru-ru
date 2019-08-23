---
title: Практическое руководство. Дополнительные возможности объектов ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 9e95c3623bf9bad8395f586392a0557ad1cde880
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912584"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="9fb44-102">Практическое руководство. Дополнительные возможности объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="9fb44-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="9fb44-103">Можно повысить удобство использования <xref:System.Windows.Forms.MenuStrip> элементов управления и <xref:System.Windows.Forms.ContextMenuStrip> следующими способами.</span><span class="sxs-lookup"><span data-stu-id="9fb44-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="9fb44-104">Добавление флажков для обозначения того, включен ли компонент или выключен, например, отображается ли линейка вдоль поля приложения для обработки текста или чтобы указать, какой файл отображается в списке файлов, например в меню **окна** .</span><span class="sxs-lookup"><span data-stu-id="9fb44-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="9fb44-105">Добавление изображений, визуально представляющих команды меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="9fb44-106">Отображать сочетания клавиш для ввода в качестве альтернативы мыши для выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="9fb44-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="9fb44-107">Например, нажатие клавиш CTRL + C выполняет команду **Copy** .</span><span class="sxs-lookup"><span data-stu-id="9fb44-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="9fb44-108">Отображение клавиш доступа для ввода альтернативных сочетаний клавиш мыши для навигации по меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="9fb44-109">Например, если нажать сочетание клавиш ALT + F, меню **файл** будет выбрано.</span><span class="sxs-lookup"><span data-stu-id="9fb44-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="9fb44-110">Отображение разделителей для группирования связанных команд и упрощения чтения меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="9fb44-111">Отображение галочки для команды меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="9fb44-112">Присвойте <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `true`свойству значение.</span><span class="sxs-lookup"><span data-stu-id="9fb44-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="9fb44-113">Это <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> свойство также задает для `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="9fb44-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="9fb44-114">Используйте эту процедуру только в том случае, если нужно, чтобы команда меню отображалась как установленная по умолчанию, независимо от того, выбрана ли она.</span><span class="sxs-lookup"><span data-stu-id="9fb44-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="9fb44-115">Чтобы отобразить галочку, которая изменяет состояние при каждом щелчке</span><span class="sxs-lookup"><span data-stu-id="9fb44-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="9fb44-116">Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true`свойства команды меню значение.</span><span class="sxs-lookup"><span data-stu-id="9fb44-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="9fb44-117">Добавление изображения в команду меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="9fb44-118">Задайте для <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойства команды меню имя изображения.</span><span class="sxs-lookup"><span data-stu-id="9fb44-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="9fb44-119">Если для <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> свойства этой команды меню задано значение или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, изображение не может быть отображено.</span><span class="sxs-lookup"><span data-stu-id="9fb44-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fb44-120">При необходимости в поле изображения также может отображаться галочка.</span><span class="sxs-lookup"><span data-stu-id="9fb44-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="9fb44-121">Кроме того, можно задать <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> для `true`свойства изображения значение, а изображение будет отображаться со штриховой рамкой вокруг него во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fb44-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="9fb44-122">Отображение сочетания клавиш для команды меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="9fb44-123">Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> свойства команды меню нужное сочетание клавиш, например CTRL + O для команды **Открыть** меню <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> , и задайте для `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="9fb44-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="9fb44-124">Отображение пользовательских сочетаний клавиш для команды меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="9fb44-125">Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойства команды меню нужное сочетание клавиш, например Ctrl + Shift + o, а не Shift + Ctrl + o, и <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> присвойте свойству `true`значение.</span><span class="sxs-lookup"><span data-stu-id="9fb44-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="9fb44-126">Отображение клавиши доступа для команды меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="9fb44-127">При задании <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства для команды меню введите амперсанд (&) перед буквой, которая должна быть подчеркнута в качестве клавиши доступа.</span><span class="sxs-lookup"><span data-stu-id="9fb44-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="9fb44-128">Например, если ввести `&Open` в <xref:System.Windows.Forms.ToolStripItem.Text%2A> качестве свойства пункта меню, команда меню будет выглядеть как перо <u>O</u>.</span><span class="sxs-lookup"><span data-stu-id="9fb44-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="9fb44-129">Чтобы перейти к этой команде меню, нажмите клавишу Alt, чтобы перевести <xref:System.Windows.Forms.MenuStrip>фокус на, и нажмите клавишу доступа к имени меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="9fb44-130">Когда меню открывается и отображает элементы с ключами доступа, достаточно нажать клавишу доступа, чтобы выбрать команду меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fb44-131">Избегайте определения повторяющихся ключей доступа, например, дважды ALT + F в одной и той же системе меню.</span><span class="sxs-lookup"><span data-stu-id="9fb44-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="9fb44-132">Невозможно гарантировать порядок выбора повторяющихся ключей доступа.</span><span class="sxs-lookup"><span data-stu-id="9fb44-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="9fb44-133">Отображение разделительной линии между командами меню</span><span class="sxs-lookup"><span data-stu-id="9fb44-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="9fb44-134">После <xref:System.Windows.Forms.MenuStrip> определения и элементов, которые он будет содержать, <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> используйте метод или <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> , чтобы <xref:System.Windows.Forms.MenuStrip> добавить команды меню и <xref:System.Windows.Forms.ToolStripSeparator> элементы управления в нужный порядок.</span><span class="sxs-lookup"><span data-stu-id="9fb44-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9fb44-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9fb44-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="9fb44-136">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="9fb44-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
