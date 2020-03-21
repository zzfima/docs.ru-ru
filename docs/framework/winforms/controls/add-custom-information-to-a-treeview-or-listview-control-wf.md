---
title: 'Как: Добавление пользовательской информации в управление TreeView или ListView'
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
ms.openlocfilehash: faed586a5814526b0169ea46c8bb452e3777d8ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182425"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)
Можно создать производный узло <xref:System.Windows.Forms.TreeView> в элементе управления форм <xref:System.Windows.Forms.ListView> Windows или элемент производное в элементе управления. Наследование позволяет добавлять любые необходимые поля, а также пользовательские методы и конструкторы для их обработки. Эту возможность можно использовать для присоединения объекта Customer к каждому узлу дерева или элементу списка. Примеры здесь для <xref:System.Windows.Forms.TreeView> управления, но тот же подход <xref:System.Windows.Forms.ListView> может быть использован для управления.  
  
### <a name="to-derive-a-tree-node"></a>Наследование узла дерева  
  
- Создайте новый класс узлов, <xref:System.Windows.Forms.TreeNode> полученный из класса, который имеет пользовательское поле для записи пути файла.  
  
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
  
2. Если вы прошли узла дерева, и <xref:System.Windows.Forms.TreeNode> он набран как класс, то вам нужно будет бросить в ваш производный класс. Приведение представляет собой явное преобразование из одного типа объекта в другой. Для получения дополнительной информации о литье, см [Неявные и явные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Литье и тип конверсии](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C ) или [Cast Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C ).  
  
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
