---
title: "Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms | Microsoft Docs"
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
  - "ListView - элемент управления [Windows Forms], примеры"
  - "Panel - элемент управления [Windows Forms], примеры"
  - "RichTextBox - элемент управления [Windows Forms], примеры"
  - "SplitContainer - элемент управления [Windows Forms], примеры"
  - "Splitter - элемент управления [Windows Forms], примеры"
  - "TreeView - элемент управления [Windows Forms], примеры"
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms
В следующей процедуре создается пользовательский интерфейс с несколькими областями, похожий на интерфейс, используемый в Microsoft Outlook, где имеется список **Папка**, область **Сообщения** и область **Предварительный просмотр**.  Такое расположение элементов достигается главным образом за счет закрепления элементов управления внутри форм.  
  
 При закреплении элемента управления необходимо решить, к какому краю родительского контейнера его следует прикрепить.  Таким образом, если для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> задать значение <xref:System.Windows.Forms.DockStyle>, правый край элемента управления закрепляется на правом крае родительского элемента управления.  При этом размер прикрепленного края элемента управления изменяется с учетом размера элемента управления контейнерного типа.  Дополнительные сведения об использовании свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> см. в разделе [Практическое руководство. Закрепление элементов управления в формах Windows Forms.](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Эта процедура предназначена для расположения элемента управления <xref:System.Windows.Forms.SplitContainer> и других элементов в форме, а не для добавления дополнительных функциональных возможностей и имитации Microsoft Outlook.  
  
 Для создания пользовательского интерфейса следует расположить все элементы управления внутри элемента управления <xref:System.Windows.Forms.SplitContainer>, в левой панели которого находится элемент управления <xref:System.Windows.Forms.TreeView>.  В правой панели элемента управления <xref:System.Windows.Forms.SplitContainer> содержится второй элемент управления <xref:System.Windows.Forms.SplitContainer>, причем элемент управления <xref:System.Windows.Forms.ListView> находится выше элемента управления <xref:System.Windows.Forms.RichTextBox>.  Эти элементы управления <xref:System.Windows.Forms.SplitContainer> позволяют независимо изменять размер других элементов управления в форме.  Используемые в данном примере методы можно изменять для создания пользовательских интерфейсов, отвечающих конкретным требованиям.  
  
### Создание пользовательского интерфейса типа Outlook программным способом  
  
1.  Объявите в форме все элементы управления, составляющие ее пользовательский интерфейс.  В данном примере для создания интерфейса в стиле Microsoft Outlook используются элементы управления <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer> и <xref:System.Windows.Forms.RichTextBox>.  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
  
    ```  
  
2.  Создайте процедуру, определяющую пользовательский интерфейс.  Нижеследующий код устанавливает свойства таким образом, что форма приобретает вид, схожий с Microsoft Outlook.  Однако таким же образом можно легко создавать другие, не менее гибкие пользовательские интерфейсы, используя для этого другие элементы управления или иначе их закрепляя.  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
  
    ```  
  
3.  В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] добавьте вызов процедуры, которая была только что создана в процедуре `New()`.  В [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] добавьте в конструктор класса формы следующую строку кода.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)