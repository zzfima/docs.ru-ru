---
title: Пользовательские составные конструкторы - средство представления элементов рабочего процесса
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 31dfae70a8b95bdfd457efe7a20ce44c2ba9c61f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715187"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="75e06-102">Пользовательские составные конструкторы - средство представления элементов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="75e06-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="75e06-103"><xref:System.Activities.Presentation.WorkflowItemPresenter> — это тип ключа в модели программирования конструктора WF, который позволяет создавать "Drop Zone", где можно разместить произвольное действие.</span><span class="sxs-lookup"><span data-stu-id="75e06-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="75e06-104">В этом образце показано, как создать конструктор действий, который охватывает такую "область перетаскивания".</span><span class="sxs-lookup"><span data-stu-id="75e06-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

 <span data-ttu-id="75e06-105">В этом образце показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75e06-105">This sample demonstrates:</span></span>

## <a name="demonstrates"></a><span data-ttu-id="75e06-106">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="75e06-106">Demonstrates</span></span>

- <span data-ttu-id="75e06-107">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="75e06-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="75e06-108">Регистрация пользовательского конструктора с использованием хранилища метаданных.</span><span class="sxs-lookup"><span data-stu-id="75e06-108">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="75e06-109">Программирование повторно размещенной области элементов декларативно и принудительно.</span><span class="sxs-lookup"><span data-stu-id="75e06-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="75e06-110">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="75e06-110">Sample Details</span></span>
 <span data-ttu-id="75e06-111">Код для этого образца показывает следующее:</span><span class="sxs-lookup"><span data-stu-id="75e06-111">The code for this sample shows:</span></span>

- <span data-ttu-id="75e06-112">Для класса `SimpleNativeActivity` создается конструктор пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="75e06-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="75e06-113">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="75e06-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
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

 <span data-ttu-id="75e06-114">Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Body`.</span><span class="sxs-lookup"><span data-stu-id="75e06-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="75e06-115">`ModelItem` — это свойство для <xref:System.Activities.Presentation.ActivityDesigner>, которое ссылается на базовый объект, для которого используется конструктор, в данном случае **симпленативеактивити**.</span><span class="sxs-lookup"><span data-stu-id="75e06-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="75e06-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="75e06-116">To setup, build, and run the sample</span></span>

1. <span data-ttu-id="75e06-117">Откройте решение в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="75e06-117">Open the solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="75e06-118">Чтобы скомпилировать и запустить приложение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="75e06-118">Press F5 to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75e06-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="75e06-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="75e06-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="75e06-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="75e06-121">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="75e06-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="75e06-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="75e06-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="75e06-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="75e06-123">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="75e06-124">Разработка приложений с помощью конструктора рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="75e06-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
