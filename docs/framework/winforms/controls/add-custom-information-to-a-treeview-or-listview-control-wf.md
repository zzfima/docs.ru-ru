---
title: Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)
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
ms.openlocfilehash: f588a00c430eb1ae1f0cdcde6b7dd22f0c8671c5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956999"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="3492b-102">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3492b-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="3492b-103">Можно создать производный узел в элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> или производном элементе <xref:System.Windows.Forms.ListView> в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="3492b-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="3492b-104">Наследование позволяет добавлять любые необходимые поля, а также пользовательские методы и конструкторы для их обработки.</span><span class="sxs-lookup"><span data-stu-id="3492b-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="3492b-105">Эту возможность можно использовать для присоединения объекта Customer к каждому узлу дерева или элементу списка.</span><span class="sxs-lookup"><span data-stu-id="3492b-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="3492b-106">Приведенные здесь примеры относятся <xref:System.Windows.Forms.TreeView> к элементу управления, но этот же подход можно использовать <xref:System.Windows.Forms.ListView> для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3492b-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="3492b-107">Наследование узла дерева</span><span class="sxs-lookup"><span data-stu-id="3492b-107">To derive a tree node</span></span>  
  
- <span data-ttu-id="3492b-108">Создайте новый класс Node, производный от <xref:System.Windows.Forms.TreeNode> класса, который имеет настраиваемое поле для записи пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="3492b-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
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
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="3492b-109">Использование производного узла дерева</span><span class="sxs-lookup"><span data-stu-id="3492b-109">To use a derived tree node</span></span>  
  
1. <span data-ttu-id="3492b-110">Новый производный узел дерева можно использовать в качестве параметра для вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="3492b-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="3492b-111">В следующем примере в качестве расположения текстового файла выбрана папка "Мои документы".</span><span class="sxs-lookup"><span data-stu-id="3492b-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="3492b-112">Это сделано, поскольку предполагается, что большинство компьютеров, работающих под управлением операционной системы Windows, содержат эту папку.</span><span class="sxs-lookup"><span data-stu-id="3492b-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="3492b-113">Это также позволяет пользователям с минимальным уровнем доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="3492b-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
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
  
2. <span data-ttu-id="3492b-114">Если передается узел дерева и он типизирован как <xref:System.Windows.Forms.TreeNode> класс, необходимо привести его к производному классу.</span><span class="sxs-lookup"><span data-stu-id="3492b-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="3492b-115">Приведение представляет собой явное преобразование из одного типа объекта в другой.</span><span class="sxs-lookup"><span data-stu-id="3492b-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="3492b-116">Дополнительные сведения о приведении см. в разделе явные и неявные [преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), приведение C# [и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (визуальный элемент) или [оператор приведения: ()](/cpp/cpp/cast-operator-parens) (визуальный C++элемент).</span><span class="sxs-lookup"><span data-stu-id="3492b-116">For more information on casting, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Casting and type conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3492b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3492b-117">See also</span></span>

- [<span data-ttu-id="3492b-118">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="3492b-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="3492b-119">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="3492b-119">ListView Control</span></span>](listview-control-windows-forms.md)
