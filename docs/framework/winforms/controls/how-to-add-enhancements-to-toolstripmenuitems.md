---
title: "Практическое руководство. Дополнительные возможности элементов ToolStripMenuItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "флажки, добавление в меню"
  - "команды [Windows Forms], группирование в меню"
  - "изображения [Windows Forms], добавление в меню"
  - "сочетания клавиш, отображение в меню"
  - "пункты меню, добавление галочек"
  - "пункты меню, добавление изображений"
  - "пункты меню, отображение клавиш быстрого вызова"
  - "пункты меню, отображение сочетаний клавиш"
  - "пункты меню, отображение разделителей"
  - "меню, группирование команд"
  - "разделители, отображение в меню"
  - "ToolStripMenuItem - элементы"
  - "ToolStripMenuItem - элементы, добавление галочек"
  - "ToolStripMenuItem - элементы, добавление изображений"
  - "ToolStripMenuItem - элементы, отображение клавиш быстрого вызова"
  - "ToolStripMenuItem - элементы, отображение сочетаний клавиш"
  - "ToolStripMenuItem - элементы, отображение разделителей"
  - "ToolStripSeparators, отображение в MenuStrip"
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Дополнительные возможности элементов ToolStripMenuItem
Дополнительных возможностей элементов управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> можно добиться следующим образом:  
  
-   Добавьте галочки для обозначения состояния \(включено или выключено\) средства \(например, для отображения линейки вдоль поля текстового редактора\) или для обозначения файла, отображаемого в списке файлов \(например, в меню **Window**\).  
  
-   Добавьте изображения, визуально представляющие команды меню.  
  
-   Отобразите сочетания клавиш в качестве клавиатурной альтернативы мыши для выполнения команд.  Например, нажатием сочетания CTRL\+C можно выполнить команду **Copy**.  
  
-   Отобразите клавиши быстрого вызова в качестве клавиатурной альтернативы мыши для перехода по меню.  Например, нажатием сочетания ALT\+F можно выбрать меню **Файл**.  
  
-   Отобразите разделители, чтобы сгруппировать связанные команды и сделать меню удобочитаемыми.  
  
### Отображение галочки в команде меню  
  
-   Установите для свойства <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> значение `true`.  
  
     При этом свойству <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> присваивается значение `true`.  Используйте эту процедуру только в том случае, если необходимо, чтобы команда меню была отмечена галочкой по умолчанию, независимо от того выбрана она или нет.  
  
### Отображение галочки, изменяющей состояние по каждому щелчку  
  
-   Свойству <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> команды меню присвойте значение `true`.  
  
### Добавление изображения в команду меню  
  
-   Свойству <xref:System.Windows.Forms.ToolStripItem.Image%2A> команды меню присвойте имя изображения.  Если свойство <xref:System.Windows.Forms.ToolStripItemDisplayStyle> этой команды меню равно <xref:System.Windows.Forms.ToolStripItemDisplayStyle> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, изображение не будет отображаться.  
  
> [!NOTE]
>  По желанию в поле изображения также может отображаться галочка.  Кроме того, свойству <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> изображения можно присвоить значение `true`, и во время выполнения граница изображения будет заштрихованной.  
  
### Отображение сочетания клавиш в команде меню  
  
-   Свойству <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> команды меню присвойте желаемое сочетание клавиш, такое как CTRL\+O для команды меню **Открыть**, а свойству <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> присвойте значение `true`.  
  
### Отображение пользовательских сочетаний клавиш в команде меню  
  
-   Свойству <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> команды меню присвойте желаемое сочетание клавиш, такое как CTRL\+SHIFT\+O, но не SHIFT\+CTRL\+O, а свойству <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> присвойте значение `true`.  
  
### Отображение клавиши быстрого вызова для команды меню  
  
-   При установке свойства <xref:System.Windows.Forms.ToolStripItem.Text%2A> для команды меню перед буквой, которая будет выделена подчеркиванием, обозначая клавишу быстрого вызова, введите знак "&".  Например, если в свойстве <xref:System.Windows.Forms.ToolStripItem.Text%2A> пункта меню указать  `&Open` , команда меню будет иметь следующий вид: **О**ткрыть.  
  
     Чтобы перейти к этой команде меню, нажмите клавишу ALT, чтобы передать фокус <xref:System.Windows.Forms.MenuStrip>, а затем нажмите клавишу доступа для меню.  Когда меню откроется, и появятся пункты меню с клавишами быстрого вызова, для выбора команды меню потребуется нажать соответствующую клавишу.  
  
> [!NOTE]
>  Не следует определять одинаковые клавиши быстрого вызова, например определять клавиши ALT\+F дважды в одной системе меню.  Порядок выбора одинаковых клавиш быстрого вызова не гарантируется в этом случае.  
  
### Отображение разделителя между командами меню  
  
-   После определения <xref:System.Windows.Forms.MenuStrip> и его элементов, используйте метод <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> или <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> для добавления команд меню или элементов управления <xref:System.Windows.Forms.ToolStripSeparator> в <xref:System.Windows.Forms.MenuStrip> в требуемом порядке.  
  
     \[Visual Basic\]  
  
    ```  
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
  
     \[C\#\]  
  
    ```  
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
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)