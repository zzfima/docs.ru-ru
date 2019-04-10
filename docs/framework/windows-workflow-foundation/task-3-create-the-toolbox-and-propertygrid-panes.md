---
title: Задача 3. Создание области элементов и сетки свойств
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 15e5b4ea08b6bc243484b6963c1c06f448bb985b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306026"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="58ca3-102">Задача 3. Создание области элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="58ca3-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="58ca3-103">В этой задаче вы создадите **элементов** и **PropertyGrid** областей и добавлять их в повторно размещенном [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58ca3-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="58ca3-104">Для ссылки, код, который должен содержаться в файле MainWindow.xaml.cs после выполнения трех задач в [повторное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md) ряд разделов указан в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="58ca3-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="58ca3-105">Создание области элементов и ее добавление к сетке.</span><span class="sxs-lookup"><span data-stu-id="58ca3-105">To create the Toolbox and add it to the grid</span></span>  
  
1. <span data-ttu-id="58ca3-106">Откройте проект HostingApplication, полученный с помощью процедуры, описанной в [задаче 2: Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="58ca3-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>  
  
2. <span data-ttu-id="58ca3-107">В **обозревателе решений** панели, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="58ca3-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3. <span data-ttu-id="58ca3-108">Добавить `GetToolboxControl` метод `MainWindow` класс, который создает <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, добавляет новую **элементов** категорию, чтобы **элементов**и назначает <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence> типы действий к этой категории.</span><span class="sxs-lookup"><span data-stu-id="58ca3-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4. <span data-ttu-id="58ca3-109">Добавьте закрытый `AddToolbox` метод `MainWindow` класс, который помещает **элементов** в левом столбце сетки.</span><span class="sxs-lookup"><span data-stu-id="58ca3-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. <span data-ttu-id="58ca3-110">Добавьте вызов метода `AddToolBox` в конструктор класса `MainWindow()`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="58ca3-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. <span data-ttu-id="58ca3-111">Нажмите клавишу F5, чтобы построить и выполнить решение.</span><span class="sxs-lookup"><span data-stu-id="58ca3-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="58ca3-112">**Элементов** содержащий <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence> действия должны отображаться.</span><span class="sxs-lookup"><span data-stu-id="58ca3-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="58ca3-113">Создание области PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="58ca3-113">To create the PropertyGrid</span></span>  
  
1. <span data-ttu-id="58ca3-114">В **обозревателе решений** панели, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="58ca3-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2. <span data-ttu-id="58ca3-115">Добавить `AddPropertyInspector` метод `MainWindow` класса для размещения **PropertyGrid** области в самом правом столбце сетки.</span><span class="sxs-lookup"><span data-stu-id="58ca3-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. <span data-ttu-id="58ca3-116">Добавьте вызов метода `AddPropertyInspector` в конструктор класса `MainWindow()`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="58ca3-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
    ```  
  
4. <span data-ttu-id="58ca3-117">Нажмите клавишу F5 для построения и выполнения решения.</span><span class="sxs-lookup"><span data-stu-id="58ca3-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="58ca3-118">**Элементов**, визуальной разработки рабочего процесса, и **PropertyGrid** области должны отображаться, а при перетаскивании <xref:System.Activities.Statements.Assign> действия или <xref:System.Activities.Statements.Sequence> действия на холст конструктора Сетка свойств должна обновиться в зависимости от выделенного действия.</span><span class="sxs-lookup"><span data-stu-id="58ca3-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58ca3-119">Пример</span><span class="sxs-lookup"><span data-stu-id="58ca3-119">Example</span></span>  
 <span data-ttu-id="58ca3-120">Теперь файл MainWindow.xaml.cs должен содержать следующий код.</span><span class="sxs-lookup"><span data-stu-id="58ca3-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="58ca3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="58ca3-121">See also</span></span>

- [<span data-ttu-id="58ca3-122">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="58ca3-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="58ca3-123">Задача 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="58ca3-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="58ca3-124">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="58ca3-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
