---
title: Практическое руководство. Дополнительные возможности элементов ToolStripMenuItem
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
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182324"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="3b0e1-102">Практическое руководство. Дополнительные возможности элементов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="3b0e1-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="3b0e1-103">Вы можете повысить <xref:System.Windows.Forms.MenuStrip> удобство <xref:System.Windows.Forms.ContextMenuStrip> использования и элементы управления следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3b0e1-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="3b0e1-104">Добавьте чековые отметки, чтобы определить, включена или выключена функция, например, отображается ли линейка по краю приложения для обработки слов, или чтобы указать, какой файл в списке файлов отображается, например, в меню **Window.**</span><span class="sxs-lookup"><span data-stu-id="3b0e1-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="3b0e1-105">Добавьте изображения, визуально представляющие команды меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="3b0e1-106">Отображение клавиш и стрижек, чтобы предоставить клавиатуру альтернативу мыши для выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="3b0e1-107">Например, нажатие CTRL-C выполняет команду **Copy.**</span><span class="sxs-lookup"><span data-stu-id="3b0e1-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="3b0e1-108">Отобразите клавиши доступа, чтобы предоставить клавиатуру альтернативу мыши для навигации меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="3b0e1-109">Например, нажатие НА ALT-F выбирает меню **файла.**</span><span class="sxs-lookup"><span data-stu-id="3b0e1-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="3b0e1-110">Отображайте бары сепаратора в групповых командах и делайте меню более читаемыми.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="3b0e1-111">Отобразить контрольную отметку в команде меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="3b0e1-112">Установите <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свое `true`свойство.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="3b0e1-113">Это также <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> устанавливает `true`свойство .</span><span class="sxs-lookup"><span data-stu-id="3b0e1-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="3b0e1-114">Используйте эту процедуру только в том случае, если вы хотите, чтобы команда меню выглядела проверенной по умолчанию, независимо от того, выбрана ли она.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="3b0e1-115">Отобразить контрольный знак, изменяемый состояние с каждым щелчком мыши</span><span class="sxs-lookup"><span data-stu-id="3b0e1-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="3b0e1-116">Установите <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойство команды `true`меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="3b0e1-117">Добавление изображения в команду меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="3b0e1-118">Установите <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойство команды меню к названию изображения.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="3b0e1-119">Если <xref:System.Windows.Forms.ToolStripItemDisplayStyle> свойство этой команды меню <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>настроено или не может отображаться.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b0e1-120">Маржа изображения также может показать чековую отметку, если вы того пожелаете.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="3b0e1-121">Кроме того, вы <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> можете установить `true`свойство изображения, и изображение появится с вылупившихся границы вокруг него во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="3b0e1-122">Отобразить ключ с коротким экраном для команды меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="3b0e1-123">Установите <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> свойство команды меню в нужную комбинацию клавиатуры, например CTRL-O `true`для команды **Открытого** меню, и установите <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> свойство для .</span><span class="sxs-lookup"><span data-stu-id="3b0e1-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="3b0e1-124">Отображение пользовательских ключей ярлыка для команды меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="3b0e1-125">Установите <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойство команды меню в желаемую комбинацию клавиатуры, например, CTRL-SHIFT-O, <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> а `true`не SHIFT-CTRL-O, и установите свойство для .</span><span class="sxs-lookup"><span data-stu-id="3b0e1-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="3b0e1-126">Отобразить ключ доступа для команды меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="3b0e1-127">При установке <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства для команды меню введите амперсанд (&) перед письмом, которое вы хотите подчеркнуть в качестве ключа доступа.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="3b0e1-128">Например, ввод `&Open` <xref:System.Windows.Forms.ToolStripItem.Text%2A> в качестве свойства элемента меню приведет к тому, что команда меню будет отосвобождаться как <u>O</u>pen.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="3b0e1-129">Чтобы перейти к этой команде меню, <xref:System.Windows.Forms.MenuStrip>нажмите ALT, чтобы уделить фокус упор на имя меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="3b0e1-130">Когда меню открывается и показывает элементы с ключами доступа, вам нужно только нажать ключ доступа, чтобы выбрать команду меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b0e1-131">Избегайте определения дубликатов ключей доступа, таких как определение ALT-F дважды в одной и той же системе меню.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="3b0e1-132">Порядок выбора дубликатов ключей доступа не может быть гарантирован.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="3b0e1-133">Отображение сепаратора между командами меню</span><span class="sxs-lookup"><span data-stu-id="3b0e1-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="3b0e1-134">После определения <xref:System.Windows.Forms.MenuStrip> ваших и элементов, которые <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> он будет содержать, используйте или метод, чтобы добавить команды меню и <xref:System.Windows.Forms.ToolStripSeparator> элементы управления <xref:System.Windows.Forms.MenuStrip> в заказе, который вы хотите.</span><span class="sxs-lookup"><span data-stu-id="3b0e1-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b0e1-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b0e1-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3b0e1-136">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3b0e1-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
