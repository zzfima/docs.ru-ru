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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Практическое руководство. Дополнительные возможности элементов ToolStripMenuItem
Вы можете повысить <xref:System.Windows.Forms.MenuStrip> удобство <xref:System.Windows.Forms.ContextMenuStrip> использования и элементы управления следующим образом:  
  
- Добавьте чековые отметки, чтобы определить, включена или выключена функция, например, отображается ли линейка по краю приложения для обработки слов, или чтобы указать, какой файл в списке файлов отображается, например, в меню **Window.**  
  
- Добавьте изображения, визуально представляющие команды меню.  
  
- Отображение клавиш и стрижек, чтобы предоставить клавиатуру альтернативу мыши для выполнения команд. Например, нажатие CTRL-C выполняет команду **Copy.**  
  
- Отобразите клавиши доступа, чтобы предоставить клавиатуру альтернативу мыши для навигации меню. Например, нажатие НА ALT-F выбирает меню **файла.**  
  
- Отображайте бары сепаратора в групповых командах и делайте меню более читаемыми.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Отобразить контрольную отметку в команде меню  
  
- Установите <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свое `true`свойство.  
  
     Это также <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> устанавливает `true`свойство . Используйте эту процедуру только в том случае, если вы хотите, чтобы команда меню выглядела проверенной по умолчанию, независимо от того, выбрана ли она.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Отобразить контрольный знак, изменяемый состояние с каждым щелчком мыши  
  
- Установите <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойство команды `true`меню.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Добавление изображения в команду меню  
  
- Установите <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойство команды меню к названию изображения. Если <xref:System.Windows.Forms.ToolStripItemDisplayStyle> свойство этой команды меню <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>настроено или не может отображаться.  
  
> [!NOTE]
> Маржа изображения также может показать чековую отметку, если вы того пожелаете. Кроме того, вы <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> можете установить `true`свойство изображения, и изображение появится с вылупившихся границы вокруг него во время выполнения.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Отобразить ключ с коротким экраном для команды меню  
  
- Установите <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> свойство команды меню в нужную комбинацию клавиатуры, например CTRL-O `true`для команды **Открытого** меню, и установите <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> свойство для .  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Отображение пользовательских ключей ярлыка для команды меню  
  
- Установите <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойство команды меню в желаемую комбинацию клавиатуры, например, CTRL-SHIFT-O, <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> а `true`не SHIFT-CTRL-O, и установите свойство для .  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Отобразить ключ доступа для команды меню  
  
- При установке <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства для команды меню введите амперсанд (&) перед письмом, которое вы хотите подчеркнуть в качестве ключа доступа. Например, ввод `&Open` <xref:System.Windows.Forms.ToolStripItem.Text%2A> в качестве свойства элемента меню приведет к тому, что команда меню будет отосвобождаться как <u>O</u>pen.
  
     Чтобы перейти к этой команде меню, <xref:System.Windows.Forms.MenuStrip>нажмите ALT, чтобы уделить фокус упор на имя меню. Когда меню открывается и показывает элементы с ключами доступа, вам нужно только нажать ключ доступа, чтобы выбрать команду меню.  
  
> [!NOTE]
> Избегайте определения дубликатов ключей доступа, таких как определение ALT-F дважды в одной и той же системе меню. Порядок выбора дубликатов ключей доступа не может быть гарантирован.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Отображение сепаратора между командами меню  
  
- После определения <xref:System.Windows.Forms.MenuStrip> ваших и элементов, которые <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> он будет содержать, используйте или метод, чтобы добавить команды меню и <xref:System.Windows.Forms.ToolStripSeparator> элементы управления <xref:System.Windows.Forms.MenuStrip> в заказе, который вы хотите.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
