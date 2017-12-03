---
title: "Как создать настраиваемый конструктор действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0b1f27af6b4ec372b9dbd63e4bc89a5c435efe6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="3a812-102">Как создать настраиваемый конструктор действий</span><span class="sxs-lookup"><span data-stu-id="3a812-102">How to: Create a Custom Activity Designer</span></span>
<span data-ttu-id="3a812-103">Пользовательские конструкторы действий обычно реализуются таким образом, что их связанные действия сочетаются с другими действиями, конструкторы которых могут помещаться вместе с ними на область конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a812-103">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="3a812-104">Эта функциональность требует, что пользовательский конструктор действий предоставлял «зону перетаскивания» для которых может быть помещено произвольное действие, а также средства для управления результирующей коллекцией элементов в рабочей области конструирования.</span><span class="sxs-lookup"><span data-stu-id="3a812-104">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="3a812-105">В этом разделе описано создание пользовательского конструктора действий, содержащего «зону перетаскивания», а также создание пользовательского конструктора действий, предоставляющего функции редактирования, необходимые для управления коллекцией элементов конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a812-105">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>  
  
 <span data-ttu-id="3a812-106">Пользовательские конструкторы действий обычно наследуют от <xref:System.Activities.Presentation.ActivityDesigner>, который является базовым типом конструктора действий по умолчанию для любых действий без определенного конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a812-106">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="3a812-107">Этот тип обеспечивает взаимодействие с таблицей свойств во время разработки и настройку основных аспектов, например, управления цветами и значками.</span><span class="sxs-lookup"><span data-stu-id="3a812-107">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>  
  
 <span data-ttu-id="3a812-108">Для упрощения разработки пользовательских конструкторов действий в конструкторе <xref:System.Activities.Presentation.ActivityDesigner> используют два элемента управления помощника, <xref:System.Activities.Presentation.WorkflowItemPresenter> и <xref:System.Activities.Presentation.WorkflowItemsPresenter>.</span><span class="sxs-lookup"><span data-stu-id="3a812-108"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="3a812-109">Они обрабатывают общие функции, например перетаскивание дочерних элементов, удаление, выделение и добавление этих дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="3a812-109">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="3a812-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> Позволяет один дочерний элемент пользовательского интерфейса, предоставляя «зону перетаскивания» а <xref:System.Activities.Presentation.WorkflowItemsPresenter> может предоставить поддерживает несколько элементов пользовательского интерфейса, включая дополнительные функции, как упорядочение, перемещение, удаление и добавление дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="3a812-110">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>  
  
 <span data-ttu-id="3a812-111">Другая важная часть описания, которую необходимо выделить в реализации пользовательских конструкторов действий, относится к способу привязывания визуальных изменений с использованием привязки данных [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] к хранящемуся в памяти экземпляру объекта, который изменяется в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="3a812-111">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="3a812-112">Это достигается с помощью дерева элементов модели, которое также обеспечивает уведомления об изменениях и отслеживание таких событий, как изменения состояний.</span><span class="sxs-lookup"><span data-stu-id="3a812-112">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>  
  
 <span data-ttu-id="3a812-113">В данном подразделе описаны две процедуры.</span><span class="sxs-lookup"><span data-stu-id="3a812-113">This topic outlines two procedures.</span></span>  
  
1.  <span data-ttu-id="3a812-114">Первая процедура описывает создание пользовательских конструкторов действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>, предоставляющим «зону перетаскивания», в которую можно помещать другие действия.</span><span class="sxs-lookup"><span data-stu-id="3a812-114">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="3a812-115">Эта процедура основана на [пользовательские составные конструкторы - средство представления элементов рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) образца.</span><span class="sxs-lookup"><span data-stu-id="3a812-115">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>  
  
2.  <span data-ttu-id="3a812-116">Вторая процедура описывает создание пользовательских конструкторов действий с элементом управления помощника <xref:System.Activities.Presentation.WorkflowItemsPresenter>, предоставляющим функции, необходимые для изменения коллекции содержащихся в нем элементов.</span><span class="sxs-lookup"><span data-stu-id="3a812-116">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="3a812-117">Эта процедура основана на [пользовательские составные конструкторы - средство представления элементов рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) образца.</span><span class="sxs-lookup"><span data-stu-id="3a812-117">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="3a812-118">Создание пользовательского конструктора действий с "зоной сброса" с использованием WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="3a812-118">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>  
  
1.  <span data-ttu-id="3a812-119">Запустите [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a812-119">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a812-120">На **файл** последовательно выберите пункты **New**, а затем выберите **проекта...** .</span><span class="sxs-lookup"><span data-stu-id="3a812-120">On the **File** menu, point to **New**, and then select **Project…**.</span></span>  
  
     <span data-ttu-id="3a812-121">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="3a812-121">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="3a812-122">В **установленные шаблоны** выберите **Windows** из категории предпочтительного языка.</span><span class="sxs-lookup"><span data-stu-id="3a812-122">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>  
  
4.  <span data-ttu-id="3a812-123">В **шаблоны** выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="3a812-123">In the **Templates** pane, select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="3a812-124">В **имя** введите `UsingWorkflowItemPresenter`.</span><span class="sxs-lookup"><span data-stu-id="3a812-124">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>  
  
6.  <span data-ttu-id="3a812-125">В **расположение** введите каталог, в котором требуется сохранить проект, или **Обзор** для перехода к нему.</span><span class="sxs-lookup"><span data-stu-id="3a812-125">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>  
  
7.  <span data-ttu-id="3a812-126">В **решения** примите значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a812-126">In the **Solution** box, accept the default value.</span></span>  
  
8.  <span data-ttu-id="3a812-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a812-127">Click **OK**.</span></span>  
  
9. <span data-ttu-id="3a812-128">Щелкните правой кнопкой мыши файл MainWindows.xaml в **обозревателе решений**выберите **удаление** и подтвердите **ОК** в **Microsoft Visual Studio**диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3a812-128">Right-click the MainWindows.xaml file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialogue box.</span></span>  
  
10. <span data-ttu-id="3a812-129">Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в **обозревателе решений**выберите **добавить**, затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3a812-129">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3a812-130">Чтобы вызвать **Добавление нового элемента** и выберите **WPF** категории из **установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3a812-130">to bring up the **Add New Item** dialogue and select the **WPF** category from the **Installed Templates** section on the left.</span></span>  
  
11. <span data-ttu-id="3a812-131">Выберите **Window (WPF)** шаблона, назовите его `RehostingWFDesigner`и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3a812-131">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>  
  
12. <span data-ttu-id="3a812-132">Откройте файл RehostingWFDesigner.xaml file и вставьте в него следующий код, чтобы определить пользовательский интерфейс для приложения.</span><span class="sxs-lookup"><span data-stu-id="3a812-132">Open the RehostingWFDesigner.xaml file and paste the following code into it to define the UI for the application.</span></span>  
  
    ```xml  
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"  
            xmlns:sys="clr-namespace:System;assembly=mscorlib"  
            Title="Window1" Height="600" Width="900">  
        <Window.Resources>  
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>  
        </Window.Resources>  
        <Grid>  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="2*"/>  
                <ColumnDefinition Width="7*"/>  
                <ColumnDefinition Width="3*"/>  
            </Grid.ColumnDefinitions>  
            <Border Grid.Column="0">  
                <sapt:ToolboxControl Name="Toolbox">  
                    <sapt:ToolboxCategory CategoryName="Basic">  
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.Sequence  
                            </sapt:ToolboxItemWrapper.ToolName>  
                           </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.WriteLine  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.If  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.While  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                    </sapt:ToolboxCategory>  
                </sapt:ToolboxControl>  
            </Border>  
            <Border Grid.Column="1" Name="DesignerBorder"/>  
            <Border Grid.Column="2" Name="PropertyBorder"/>  
        </Grid>  
    </Window>  
    ```  
  
13. <span data-ttu-id="3a812-133">Чтобы связать конструктор действия с типом действия, необходимо зарегистрировать конструктор действия в хранилище метаданных.</span><span class="sxs-lookup"><span data-stu-id="3a812-133">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="3a812-134">Для этого добавьте метод `RegisterMetadata` в класс `RehostingWFDesigner`.</span><span class="sxs-lookup"><span data-stu-id="3a812-134">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="3a812-135">В области метода `RegisterMetadata` создайте объект <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> и вызовите метод <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>, чтобы добавить к нему атрибуты.</span><span class="sxs-lookup"><span data-stu-id="3a812-135">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="3a812-136">Вызовите метод <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>, чтобы добавить <xref:System.Activities.Presentation.Metadata.AttributeTable> в хранилище метаданных.</span><span class="sxs-lookup"><span data-stu-id="3a812-136">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="3a812-137">Следующий код содержит логику повторного размещения для конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a812-137">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="3a812-138">Он регистрирует метаданные, помещает действие `SimpleNativeActivity` в область элементов и создает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="3a812-138">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="3a812-139">Поместите этот код в файл RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="3a812-139">Put this code into the RehostingWFDesigner.xaml.cs file.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Presentation.Toolbox;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        // Interaction logic for RehostingWFDesigner.xaml  
        public partial class RehostingWFDesigner  
        {  
            public RehostingWFDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
                // add custom activity to toolbox  
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));  
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
14. <span data-ttu-id="3a812-140">Щелкните правой кнопкой мыши папку References в обозревателе решений и выберите **добавить ссылку...**</span><span class="sxs-lookup"><span data-stu-id="3a812-140">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="3a812-141">Чтобы вызвать **добавить ссылку** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="3a812-141">to bring up the **Add Reference** dialogue.</span></span>  
  
15. <span data-ttu-id="3a812-142">Нажмите кнопку **.NET** найдите сборку с именем **System.Activities.Core.Presentation**, выделите его и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a812-142">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>  
  
16. <span data-ttu-id="3a812-143">Таким же образом добавьте ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="3a812-143">Using the same procedure, add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="3a812-144">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="3a812-144">System.Data.DataSetExtensions.dll</span></span>  
  
    2.  <span data-ttu-id="3a812-145">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="3a812-145">System.Activities.Presentation.dll</span></span>  
  
    3.  <span data-ttu-id="3a812-146">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="3a812-146">System.ServiceModel.Activities.dll</span></span>  
  
17. <span data-ttu-id="3a812-147">Откройте файл App.xaml и измените значение StartUpUri на «RehostingWFDesigner.xaml».</span><span class="sxs-lookup"><span data-stu-id="3a812-147">Open the App.xaml file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>  
  
18. <span data-ttu-id="3a812-148">Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в **обозревателе решений**выберите **добавить**, затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3a812-148">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3a812-149">Чтобы вызвать **Добавление нового элемента** и выберите **рабочего процесса** категорию **установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3a812-149">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
19. <span data-ttu-id="3a812-150">Выберите **конструктора** шаблона, назовите его `SimpleNativeDesigner`и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3a812-150">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>  
  
20. <span data-ttu-id="3a812-151">Откройте файл SimpleNativeDesigner.xaml и вставьте в него следующий код.</span><span class="sxs-lookup"><span data-stu-id="3a812-151">Open the SimpleNativeDesigner.xaml file and paste the following code into it.</span></span> <span data-ttu-id="3a812-152">Обратите внимание, что этот код использует <xref:System.Activities.Presentation.ActivityDesigner> в качестве корневого элемента и показывает, как привязка используется для интеграции <xref:System.Activities.Presentation.WorkflowItemPresenter> в конструктор, чтобы дочерний тип можно было отобразить в конструкторе составных действий.</span><span class="sxs-lookup"><span data-stu-id="3a812-152">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a812-153">Схема для <xref:System.Activities.Presentation.ActivityDesigner> позволяет добавлять только один дочерний элемент в определение пользовательского конструктора действий. Однако этим элементом может быть `StackPanel`, `Grid` или другой составной элемент пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a812-153">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <StackPanel>  
                    <TextBlock>This is the collapsed view</TextBlock>  
                </StackPanel>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock>Custom Text</TextBlock>  
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                            HintText="Please drop an activity here" />  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
21. <span data-ttu-id="3a812-154">Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в **обозревателе решений**выберите **добавить**, затем **новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="3a812-154">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="3a812-155">Чтобы вызвать **Добавление нового элемента** и выберите **рабочего процесса** категорию **установленные шаблоны** слева.</span><span class="sxs-lookup"><span data-stu-id="3a812-155">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
22. <span data-ttu-id="3a812-156">Выберите **действие кода** шаблона, назовите его `SimpleNativeActivity`и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="3a812-156">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>  
  
23. <span data-ttu-id="3a812-157">Реализуйте класс `SimpleNativeActivity`, введя следующий код в файл SimpleNativeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="3a812-157">Implement the `SimpleNativeActivity` class by entering the following code into the SimpleNativeActivity.cs file.</span></span>  
  
    ```  
    using System.Activities;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        public sealed class SimpleNativeActivity : NativeActivity  
        {  
            // this property contains an activity that will be scheduled in the execute method  
    // the WorkflowItemPresenter in the designer is bound to this to enable editing  
    // of the value  
            public Activity Body { get; set; }  
  
            protected override void CacheMetadata(NativeActivityMetadata metadata)  
            {  
               metadata.AddChild(Body);  
               base.CacheMetadata(metadata);  
  
            }  
  
            protected override void Execute(NativeActivityContext context)  
            {  
                context.ScheduleActivity(Body);  
            }  
        }  
    }  
    ```  
  
24. <span data-ttu-id="3a812-158">Выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="3a812-158">Select **Build Solution** from the **Build** menu.</span></span>  
  
25. <span data-ttu-id="3a812-159">Выберите **Запуск без отладки** из **отладки** меню, чтобы открыть окно повторно размещенный пользовательского конструктора.</span><span class="sxs-lookup"><span data-stu-id="3a812-159">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="3a812-160">Создание пользовательского конструктора действий с использованием WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="3a812-160">To create a custom activity designer using WorkflowItemsPresenter</span></span>  
  
1.  <span data-ttu-id="3a812-161">Процедура для второго пользовательского конструктора действий похожа первый с несколькими изменениями, первый из которых заключается в второму приложению имени `UsingWorkflowItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="3a812-161">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="3a812-162">Кроме того, это приложение не определяет новое пользовательское действие.</span><span class="sxs-lookup"><span data-stu-id="3a812-162">Also this application does not define a new custom activity.</span></span>  
  
2.  <span data-ttu-id="3a812-163">Основные различия находятся в файлах CustomParallelDesigner.xaml и RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="3a812-163">Key differences are contained in the CustomParallelDesigner.xaml and RehostingWFDesigner.xaml.cs files.</span></span> <span data-ttu-id="3a812-164">Ниже приводится код из файла CustomParallelDesigne.xaml, который определяет пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3a812-164">Here is the code from the CustomParallelDesigne.xaml file that defines the UI.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <TextBlock>This is the Collapsed View</TextBlock>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>  
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>  
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                        Items="{Binding Path=ModelItem.Branches}">  
                        <sap:WorkflowItemsPresenter.SpacerTemplate>  
                            <DataTemplate>  
                                <Ellipse Width="10" Height="10" Fill="Black"/>  
                            </DataTemplate>  
                        </sap:WorkflowItemsPresenter.SpacerTemplate>  
                        <sap:WorkflowItemsPresenter.ItemsPanel>  
                            <ItemsPanelTemplate>  
                                <StackPanel Orientation="Horizontal"/>  
                            </ItemsPanelTemplate>  
                        </sap:WorkflowItemsPresenter.ItemsPanel>  
                    </sap:WorkflowItemsPresenter>  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
3.  <span data-ttu-id="3a812-165">Ниже приводится код из файла RehostingWFDesigner.xaml.cs, который предоставляет логику повторного размещения.</span><span class="sxs-lookup"><span data-stu-id="3a812-165">Here is the code from the RehostingWFDesigner.xaml.cs file that provides the rehosting logic.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespaceUsingWorkflowItemsPresenter  
    {  
        public partial class RehostingWfDesigner : Window  
        {  
            public RehostingWfDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3a812-166">См. также</span><span class="sxs-lookup"><span data-stu-id="3a812-166">See Also</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 <xref:System.Activities.Presentation.WorkflowViewElement>  
 <xref:System.Activities.Presentation.Model.ModelItem>  
 [<span data-ttu-id="3a812-167">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3a812-167">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
