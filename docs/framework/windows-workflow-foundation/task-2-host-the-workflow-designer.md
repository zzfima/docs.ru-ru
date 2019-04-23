---
title: Задача 2. Размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 3f7964e907fe513679e60c18292f07c84128590b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299271"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="96bb5-102">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="96bb5-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="96bb5-103">В этом разделе описывается процедура по размещению экземпляра [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="96bb5-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="96bb5-104">Процедура выполняет настройку **сетки** элемент управления, который содержит конструктор, программным образом создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner> , содержащий значение по умолчанию <xref:System.Activities.Statements.Sequence> действия, регистрирует метаданные конструктора, чтобы предоставить Поддержка конструктора для всех встроенных действий и узлы [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="96bb5-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="96bb5-105">Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="96bb5-105">To host the workflow designer</span></span>  
  
1. <span data-ttu-id="96bb5-106">Откройте проект HostingApplication, созданный в [задаче 1: Создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="96bb5-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>  
  
2. <span data-ttu-id="96bb5-107">Отрегулируйте размер окна, чтобы было проще использовать [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96bb5-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="96bb5-108">Чтобы сделать это, выберите **MainWindow** в конструкторе, нажмите клавишу F4, чтобы открыть **свойства** окно и в **макета** раздел существует, задайте **ширины** значению, равному 600 и **высота** значение 350.</span><span class="sxs-lookup"><span data-stu-id="96bb5-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3. <span data-ttu-id="96bb5-109">Задайте имя сетки, выбрав **сетки** панель в конструкторе (щелкните поле в **MainWindow**) и параметр **имя** свойство в верхней части  **Свойства** окно, чтобы значение «grid1».</span><span class="sxs-lookup"><span data-stu-id="96bb5-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4. <span data-ttu-id="96bb5-110">В **свойства** окно, нажмите кнопку с многоточием (**...** ) рядом с полем `ColumnDefinitions` свойства, чтобы открыть **редактор коллекции** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="96bb5-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5. <span data-ttu-id="96bb5-111">В **редактор коллекции** диалоговом окне щелкните **добавить** кнопку три раза, чтобы вставить в макет три столбца.</span><span class="sxs-lookup"><span data-stu-id="96bb5-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="96bb5-112">Первый столбец будет содержать **элементов**, во втором столбце будет размещаться [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], и третий столбец будет использоваться для инспектора свойств.</span><span class="sxs-lookup"><span data-stu-id="96bb5-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6. <span data-ttu-id="96bb5-113">Задайте `Width` свойство среднего столбца значение «4 \*».</span><span class="sxs-lookup"><span data-stu-id="96bb5-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7. <span data-ttu-id="96bb5-114">Нажмите кнопку **ОК** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="96bb5-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="96bb5-115">Следующий код XAML будет добавлен в файл MainWindows.xaml.</span><span class="sxs-lookup"><span data-stu-id="96bb5-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. <span data-ttu-id="96bb5-116">В **обозревателе решений**, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="96bb5-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="96bb5-117">Измените код, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="96bb5-117">Modify the code by following these steps:</span></span>  
  
    1.  <span data-ttu-id="96bb5-118">Добавьте следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="96bb5-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <span data-ttu-id="96bb5-119">Чтобы объявить закрытый член класса для хранения экземпляра <xref:System.Activities.Presentation.WorkflowDesigner>, добавьте в класс `MainWindow` следующий код.</span><span class="sxs-lookup"><span data-stu-id="96bb5-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
        ```csharp  
        public partial class MainWindow : Window  
        {  
            private WorkflowDesigner wd;  
  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
        }  
        ```  
  
    3.  <span data-ttu-id="96bb5-120">Добавьте следующий метод `AddDesigner` в класс `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="96bb5-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="96bb5-121">Эта реализация создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, добавляет <xref:System.Activities.Statements.Sequence> действия и помещает его в средний столбец grid1 **сетки**.</span><span class="sxs-lookup"><span data-stu-id="96bb5-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
        ```csharp  
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
        ```  
  
    4.  <span data-ttu-id="96bb5-122">Зарегистрируйте метаданные конструктора, чтобы добавить поддержку конструктора для всех встроенных действий.</span><span class="sxs-lookup"><span data-stu-id="96bb5-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="96bb5-123">Это позволяет перетаскивать действия из области элементов в исходное действие <xref:System.Activities.Statements.Sequence> в [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96bb5-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="96bb5-124">Для этого добавьте метод `RegisterMetadata` в класс `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="96bb5-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         <span data-ttu-id="96bb5-125">Дополнительные сведения о регистрации конструкторов действий см. в разделе [как: Создание пользовательского конструктора действий](how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="96bb5-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5.  <span data-ttu-id="96bb5-126">В конструкторе класса `MainWindow` добавьте вызовы объявленных ранее методов для регистрации метаданных для поддержки конструктора и создания <xref:System.Activities.Presentation.WorkflowDesigner>.</span><span class="sxs-lookup"><span data-stu-id="96bb5-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="96bb5-127">Метод `RegisterMetadata` регистрирует метаданные конструктора встроенных действий, включая действие <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="96bb5-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="96bb5-128">Поскольку метод `AddDesigner` использует действие <xref:System.Activities.Statements.Sequence>, сначала необходимо вызвать метод `RegisterMetadata`.</span><span class="sxs-lookup"><span data-stu-id="96bb5-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="96bb5-129">Нажмите клавишу F5 для построения и выполнения решения.</span><span class="sxs-lookup"><span data-stu-id="96bb5-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="96bb5-130">См. в разделе [задача 3: Создание элементов и сетки свойств](task-3-create-the-toolbox-and-propertygrid-panes.md) вы научитесь добавлять **элементов** и **PropertyGrid** поддержки в повторно размещенном рабочего процесса конструктор.</span><span class="sxs-lookup"><span data-stu-id="96bb5-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bb5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="96bb5-131">See also</span></span>

- [<span data-ttu-id="96bb5-132">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="96bb5-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="96bb5-133">Упражнение 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="96bb5-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="96bb5-134">Задача 3. Создание элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="96bb5-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
