---
title: Пользовательские составные конструкторы - средство представления элементов рабочего процесса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 403b0125e6b1966d201c891448ad25ec83f42be5
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881923"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="e6192-102">Пользовательские составные конструкторы - средство представления элементов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e6192-102">Custom Composite Designers - Workflow Items Presenter</span></span>

<span data-ttu-id="e6192-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> является типом ключа в модели программирования конструктора WF, позволяющим редактирование коллекции содержащихся элементов.</span><span class="sxs-lookup"><span data-stu-id="e6192-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="e6192-104">В этом образце показано, как построить конструктор действий, который предоставляет доступ к такой изменяемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e6192-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

<span data-ttu-id="e6192-105">В этом образце показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e6192-105">This sample demonstrates:</span></span>

- <span data-ttu-id="e6192-106">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e6192-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="e6192-107">Создание конструктора действий со «свернутым» и «развернутым» представлением.</span><span class="sxs-lookup"><span data-stu-id="e6192-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

- <span data-ttu-id="e6192-108">Переопределение конструктора по умолчанию в повторно размещенном приложении.</span><span class="sxs-lookup"><span data-stu-id="e6192-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e6192-109">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e6192-109">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e6192-110">Откройте **UsingWorkflowItemsPresenter.sln** образец решения для C# или VB в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="e6192-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2. <span data-ttu-id="e6192-111">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="e6192-111">Build and run the solution.</span></span> <span data-ttu-id="e6192-112">Должно открыться повторно размещенное приложение конструктора рабочих процессов, после чего действия можно перетащить на полотно.</span><span class="sxs-lookup"><span data-stu-id="e6192-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="e6192-113">Описание образца</span><span class="sxs-lookup"><span data-stu-id="e6192-113">Sample Highlights</span></span>

<span data-ttu-id="e6192-114">Код для этого образца показывает следующее.</span><span class="sxs-lookup"><span data-stu-id="e6192-114">The code for this sample shows the following:</span></span>

- <span data-ttu-id="e6192-115">Действие, для которого построен конструктор: `Parallel`</span><span class="sxs-lookup"><span data-stu-id="e6192-115">The activity a designer is built for:  `Parallel`</span></span>

- <span data-ttu-id="e6192-116">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e6192-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e6192-117">Некоторые замечания.</span><span class="sxs-lookup"><span data-stu-id="e6192-117">A few things to point out:</span></span>

  - <span data-ttu-id="e6192-118">Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Branches`.</span><span class="sxs-lookup"><span data-stu-id="e6192-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> <span data-ttu-id="e6192-119">`ModelItem` - свойство `WorkflowElementDesigner`, которое относится к базовому объекту, для которого используется конструктор, в данном случае - `Parallel`.</span><span class="sxs-lookup"><span data-stu-id="e6192-119">`ModelItem` is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

  - <span data-ttu-id="e6192-120">Шаблон <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> может использоваться для указания видимого изображения, отображаемого между отдельными элементами коллекции.</span><span class="sxs-lookup"><span data-stu-id="e6192-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

  - <span data-ttu-id="e6192-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> является шаблоном, который может быть предоставлен для определения макета элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e6192-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="e6192-122">В данном случае используется горизонтальный элемент StackPanel.</span><span class="sxs-lookup"><span data-stu-id="e6192-122">In this case, a horizontal stack panel is used.</span></span>

  <span data-ttu-id="e6192-123">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e6192-123">This following example code shows this.</span></span>
  
  ```xaml
  <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                Items="{Binding Path=ModelItem.Branches}">
      <sad:WorkflowItemsPresenter.SpacerTemplate>
        <DataTemplate>
          <Ellipse Width="10" Height="10" Fill="Black"/>
        </DataTemplate>
      </sad:WorkflowItemsPresenter.SpacerTemplate>
      <sad:WorkflowItemsPresenter.ItemsPanel>
        <ItemsPanelTemplate>
          <StackPanel Orientation="Horizontal"/>
        </ItemsPanelTemplate>
      </sad:WorkflowItemsPresenter.ItemsPanel>
    </sad:WorkflowItemsPresenter>
  ```

- <span data-ttu-id="e6192-124">Выполнение связи объекта `DesignerAttribute` с типом `Parallel`, а затем вывод указанных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e6192-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    - <span data-ttu-id="e6192-125">Сначала зарегистрируйте все конструкторы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6192-125">First, register all of the default designers.</span></span>

    <span data-ttu-id="e6192-126">Ниже приведен пример кода.</span><span class="sxs-lookup"><span data-stu-id="e6192-126">The following is the code example.</span></span>

    ```csharp
    // register metadata
    (new DesignerMetadata()).Register();
    RegisterCustomMetadata();
    ```

    ```vb
    ' register metadata
    Dim metadata = New DesignerMetadata()
    metadata.Register()
    ' register custom metadata
    RegisterCustomMetadata()
    ```

    - <span data-ttu-id="e6192-127">Далее переопределите параллель в методе `RegisterCustomMetadata`.</span><span class="sxs-lookup"><span data-stu-id="e6192-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

    <span data-ttu-id="e6192-128">В следующем коде это показано на языках C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e6192-128">The following code shows this in C# and Visual Basic.</span></span>

    ```csharp
    void RegisterCustomMetadata()
    {
          AttributeTableBuilder builder = new AttributeTableBuilder();
          builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
          MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

    ```vb
    Sub RegisterCustomMetadata()
       Dim builder As New AttributeTableBuilder()
       builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
       MetadataStore.AddAttributeTable(builder.CreateTable())
    End Sub
    ```

- <span data-ttu-id="e6192-129">Наконец, обратите внимание на использование различных шаблонов данных и триггеров для выбора соответствующего шаблона на основании свойства `IsRootDesigner`.</span><span class="sxs-lookup"><span data-stu-id="e6192-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

  <span data-ttu-id="e6192-130">Ниже приведен пример кода.</span><span class="sxs-lookup"><span data-stu-id="e6192-130">The following is the code example.</span></span>

  ```xaml
  <sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
      xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
    <sad:ActivityDesigner.Resources>
      <DataTemplate x:Key="Expanded">
        <StackPanel>
          <TextBlock>This is the Expanded View</TextBlock>
          <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                      Items="{Binding Path=ModelItem.Branches}">
            <sad:WorkflowItemsPresenter.SpacerTemplate>
              <DataTemplate>
                <Ellipse Width="10" Height="10" Fill="Black"/>
              </DataTemplate>
            </sad:WorkflowItemsPresenter.SpacerTemplate>
            <sad:WorkflowItemsPresenter.ItemsPanel>
              <ItemsPanelTemplate>
                <StackPanel Orientation="Horizontal"/>
              </ItemsPanelTemplate>
            </sad:WorkflowItemsPresenter.ItemsPanel>
          </sad:WorkflowItemsPresenter>
        </StackPanel>
      </DataTemplate>
      <DataTemplate x:Key="Collapsed">
        <TextBlock>This is the Collapsed View</TextBlock>
      </DataTemplate>
      <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
        <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
        <Style.Triggers>
          <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
            <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
          </DataTrigger>
        </Style.Triggers>
      </Style>
    </sad: ActivityDesigner.Resources>
    <Grid>
      <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
    </Grid>
  </sad: ActivityDesigner>
  ```

> [!IMPORTANT]
> <span data-ttu-id="e6192-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6192-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6192-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e6192-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e6192-133">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="e6192-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6192-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e6192-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`

## <a name="see-also"></a><span data-ttu-id="e6192-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e6192-135">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [<span data-ttu-id="e6192-136">Разработка приложений с помощью конструктора рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e6192-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
