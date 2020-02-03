---
title: Инструкции. Добавление пользовательских сведений в элемент управления TreeView или ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: fe507c41de97e9332f3f27e453a476d992f86627
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732220"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)
Можно создать производный узел в элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> или производном элементе в элементе управления <xref:System.Windows.Forms.ListView>. Наследование позволяет добавлять любые необходимые поля, а также пользовательские методы и конструкторы для их обработки. Эту возможность можно использовать для присоединения объекта Customer к каждому узлу дерева или элементу списка. Ниже приведены примеры для элемента управления <xref:System.Windows.Forms.TreeView>, но такой же подход можно использовать и для элемента управления <xref:System.Windows.Forms.ListView>.  
  
### <a name="to-derive-a-tree-node"></a>Наследование узла дерева  
  
- Создайте новый класс Node, производный от класса <xref:System.Windows.Forms.TreeNode>, который содержит настраиваемое поле для записи пути к файлу.  
  
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
  
### <a name="to-use-a-derived-tree-node"></a>Использование производного узла дерева  
  
1. Новый производный узел дерева можно использовать в качестве параметра для вызовов функций.  
  
     В следующем примере в качестве расположения текстового файла выбрана папка "Мои документы". Это сделано, поскольку предполагается, что большинство компьютеров, работающих под управлением операционной системы Windows, содержат эту папку. Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.  
  
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
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
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
  
2. Если вы передали узел дерева, а он типизирован как класс <xref:System.Windows.Forms.TreeNode>, необходимо привести его к производному классу. Приведение представляет собой явное преобразование из одного типа объекта в другой. Дополнительные сведения о приведении см. в разделе явные [и](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) неявные преобразования (Visual Basic), [приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (визуальный C#элемент) или [оператор приведения: ()](/cpp/cpp/cast-operator-parens) (визуальный C++элемент).  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Элемент управления ListView](listview-control-windows-forms.md)
