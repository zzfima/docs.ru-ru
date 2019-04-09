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
ms.openlocfilehash: 458347df7e17aabc1e9e21d66ad1b5a96200fe28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198560"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="665ec-102">Практическое руководство. Дополнительные возможности объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="665ec-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="665ec-103">Можно повысить удобство использования <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> элементы управления одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="665ec-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="665ec-104">Добавьте галочки для обозначения включено или отключить, например, следует ли отображать линейки вдоль поля текстового редактора, или для указания файла в список файлов, отображаемых, например на **окно** меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="665ec-105">Добавление изображений, которые визуально представляют команды меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="665ec-106">Отображать сочетания клавиш, чтобы предоставить альтернативы мыши, клавиатуры для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="665ec-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="665ec-107">Например, нажатие клавиш CTRL + C выполняет **копирования** команды.</span><span class="sxs-lookup"><span data-stu-id="665ec-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="665ec-108">Отображение ключей доступа для предоставления клавиатуры вместо мыши для навигации в меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="665ec-109">Например, нажмите клавиши ALT + F, выбирает **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="665ec-110">Показать разделители, чтобы сгруппировать связанные команды и сделать меню в более удобном для чтения.</span><span class="sxs-lookup"><span data-stu-id="665ec-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="665ec-111">Чтобы отобразить метку команды меню</span><span class="sxs-lookup"><span data-stu-id="665ec-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="665ec-112">Задайте его <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="665ec-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="665ec-113">Эта команда также задает <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="665ec-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="665ec-114">Используйте эту процедуру только в том случае, если требуется, чтобы команда меню, подлежащая галочкой по умолчанию, независимо от того, установлен ли флажок.</span><span class="sxs-lookup"><span data-stu-id="665ec-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="665ec-115">Чтобы отобразить флажок, который изменяет состояние каждого щелчком</span><span class="sxs-lookup"><span data-stu-id="665ec-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="665ec-116">Команды меню <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="665ec-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="665ec-117">Добавление изображения для команды меню</span><span class="sxs-lookup"><span data-stu-id="665ec-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="665ec-118">Команды меню <xref:System.Windows.Forms.ToolStripItem.Image%2A> имя изображения.</span><span class="sxs-lookup"><span data-stu-id="665ec-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="665ec-119">Если <xref:System.Windows.Forms.ToolStripItemDisplayStyle> этой команды меню свойству <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, не удается отобразить изображение.</span><span class="sxs-lookup"><span data-stu-id="665ec-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="665ec-120">Поле изображения также можно Показать метку желанию.</span><span class="sxs-lookup"><span data-stu-id="665ec-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="665ec-121">Кроме того, можно задать <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свойство изображения `true`, а изображение будет отображаться со штриховой границей вокруг него во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="665ec-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="665ec-122">Чтобы отобразить сочетания клавиш для команды меню</span><span class="sxs-lookup"><span data-stu-id="665ec-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="665ec-123">Команды меню <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> свойства желаемое сочетание клавиш, например CTRL + O для **откройте** команды меню, а также набор <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="665ec-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="665ec-124">Чтобы отобразить настраиваемые сочетания клавиш для команды меню</span><span class="sxs-lookup"><span data-stu-id="665ec-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="665ec-125">Команды меню <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойства желаемое сочетание клавиш, например CTRL + SHIFT + O, а не SHIFT + CTRL + O и набор <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="665ec-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="665ec-126">Чтобы отобразить ключ доступа для команды меню</span><span class="sxs-lookup"><span data-stu-id="665ec-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="665ec-127">При задании <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойство для команды меню введите амперсанд (&) перед буквой, чтобы быть подчеркнуты как клавиша доступа.</span><span class="sxs-lookup"><span data-stu-id="665ec-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="665ec-128">Например, при вводе `&Open` как <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойство пункта меню приведет к команде меню, который отображается в виде <u>O</u>пера.</span><span class="sxs-lookup"><span data-stu-id="665ec-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="665ec-129">Чтобы перейти к этой команды меню, нажмите клавишу ALT, чтобы передать фокус <xref:System.Windows.Forms.MenuStrip>и нажмите клавишу доступа для меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="665ec-130">Когда откроется меню и отображаются элементы с помощью ключей доступа, необходимо только клавишу доступа, чтобы выбрать команду меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="665ec-131">Не рекомендуется определять дублирующиеся клавиши доступа, например для определения ALT + F дважды в одной и той же системе меню.</span><span class="sxs-lookup"><span data-stu-id="665ec-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="665ec-132">Невозможно гарантировать порядок выбора дублирующиеся клавиши доступа.</span><span class="sxs-lookup"><span data-stu-id="665ec-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="665ec-133">Чтобы отобразить строку разделителя между командами меню</span><span class="sxs-lookup"><span data-stu-id="665ec-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="665ec-134">После определения вашей <xref:System.Windows.Forms.MenuStrip> и элементов, которые он содержит, используйте <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> или <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> метод для добавления команды меню и <xref:System.Windows.Forms.ToolStripSeparator> элементы управления <xref:System.Windows.Forms.MenuStrip> в том порядке, в.</span><span class="sxs-lookup"><span data-stu-id="665ec-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="665ec-135">См. также</span><span class="sxs-lookup"><span data-stu-id="665ec-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="665ec-136">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="665ec-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
