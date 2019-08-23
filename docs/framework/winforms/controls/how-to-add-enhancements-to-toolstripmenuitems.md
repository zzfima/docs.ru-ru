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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>Практическое руководство. Дополнительные возможности объектов ToolStripMenuItem
Можно повысить удобство использования <xref:System.Windows.Forms.MenuStrip> элементов управления и <xref:System.Windows.Forms.ContextMenuStrip> следующими способами.  
  
- Добавление флажков для обозначения того, включен ли компонент или выключен, например, отображается ли линейка вдоль поля приложения для обработки текста или чтобы указать, какой файл отображается в списке файлов, например в меню **окна** .  
  
- Добавление изображений, визуально представляющих команды меню.  
  
- Отображать сочетания клавиш для ввода в качестве альтернативы мыши для выполнения команд. Например, нажатие клавиш CTRL + C выполняет команду **Copy** .  
  
- Отображение клавиш доступа для ввода альтернативных сочетаний клавиш мыши для навигации по меню. Например, если нажать сочетание клавиш ALT + F, меню **файл** будет выбрано.  
  
- Отображение разделителей для группирования связанных команд и упрощения чтения меню.  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>Отображение галочки для команды меню  
  
- Присвойте <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `true`свойству значение.  
  
     Это <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> свойство также задает для `true`свойства значение. Используйте эту процедуру только в том случае, если нужно, чтобы команда меню отображалась как установленная по умолчанию, независимо от того, выбрана ли она.  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>Чтобы отобразить галочку, которая изменяет состояние при каждом щелчке  
  
- Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true`свойства команды меню значение.  
  
### <a name="to-add-an-image-to-a-menu-command"></a>Добавление изображения в команду меню  
  
- Задайте для <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойства команды меню имя изображения. Если для <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> свойства этой команды меню задано значение или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, изображение не может быть отображено.  
  
> [!NOTE]
> При необходимости в поле изображения также может отображаться галочка. Кроме того, можно задать <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> для `true`свойства изображения значение, а изображение будет отображаться со штриховой рамкой вокруг него во время выполнения.  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>Отображение сочетания клавиш для команды меню  
  
- Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> свойства команды меню нужное сочетание клавиш, например CTRL + O для команды **Открыть** меню <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> , и задайте для `true`свойства значение.  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>Отображение пользовательских сочетаний клавиш для команды меню  
  
- Задайте для <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойства команды меню нужное сочетание клавиш, например Ctrl + Shift + o, а не Shift + Ctrl + o, и <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> присвойте свойству `true`значение.  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>Отображение клавиши доступа для команды меню  
  
- При задании <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства для команды меню введите амперсанд (&) перед буквой, которая должна быть подчеркнута в качестве клавиши доступа. Например, если ввести `&Open` в <xref:System.Windows.Forms.ToolStripItem.Text%2A> качестве свойства пункта меню, команда меню будет выглядеть как перо <u>O</u>.
  
     Чтобы перейти к этой команде меню, нажмите клавишу Alt, чтобы перевести <xref:System.Windows.Forms.MenuStrip>фокус на, и нажмите клавишу доступа к имени меню. Когда меню открывается и отображает элементы с ключами доступа, достаточно нажать клавишу доступа, чтобы выбрать команду меню.  
  
> [!NOTE]
> Избегайте определения повторяющихся ключей доступа, например, дважды ALT + F в одной и той же системе меню. Невозможно гарантировать порядок выбора повторяющихся ключей доступа.  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>Отображение разделительной линии между командами меню  
  
- После <xref:System.Windows.Forms.MenuStrip> определения и элементов, которые он будет содержать, <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> используйте метод или <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> , чтобы <xref:System.Windows.Forms.MenuStrip> добавить команды меню и <xref:System.Windows.Forms.ToolStripSeparator> элементы управления в нужный порядок.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
