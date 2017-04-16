---
title: "Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListItem"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], ListView - элемент управления"
  - "примеры [Windows Forms], TreeView - элемент управления"
  - "ListView - элемент управления [Windows Forms], добавление пользовательских сведений"
  - "Tag - свойство"
  - "TreeView - элемент управления [Windows Forms], добавление пользовательских сведений"
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)
Разработчик формы может создать производный узел в элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> или производный элемент списка в элементе управления <xref:System.Windows.Forms.ListView>.  Образование производных элементов позволяет добавлять любые необходимые поля, а также пользовательские методы и конструкторы для их обработки.  Эта возможность применяется, например, для добавления объекта Customer к каждому узлу дерева или элементу списка.  Примеры, приведенные в этом разделе, относятся к элементу управления <xref:System.Windows.Forms.TreeView>, но аналогичный подход может использоваться и для элемента управления <xref:System.Windows.Forms.ListView>.  
  
### Создание производного узла дерева  
  
-   Создайте новый класс узла, производный от класса <xref:System.Windows.Forms.TreeNode>, в котором предусмотрено пользовательское поле для записи пути к файлу.  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### Использование производного узла дерева  
  
1.  Новый производный узел дерева может быть использован как параметр при вызове функции.  
  
     В нижеследующем примере в качестве местоположения текстового файла выбрана папка "Мои документы".  Такой выбор объясняется тем, что эта папка имеется на большинстве компьютеров, работающих под управлением операционной системы Windows.  Кроме того, если используется эта папка, то для запуска приложения достаточен минимальный уровень доступа к системе.  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2.  Если передается узел дерева, тип которого определен как класс <xref:System.Windows.Forms.TreeNode>, то его необходимо привести к типу производного класса.  Приведение означает явное преобразование одного типа объекта в другой.  Дополнительные сведения о приведении типов см. в разделах [Явные и неявные преобразования](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\), [Оператор \(\)](../Topic/\(\)%20Operator%20\(C%23%20Reference\).md) \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) или [Оператор Cast: \(\)](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/DocumentStructure/visualbasic/spec_withstructure-xps/_rels/.rels) \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\).  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)