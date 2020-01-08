---
title: Пользовательские составные конструкторы - средство представления элементов рабочего процесса
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: d1047b8be35545e83eaa8788b53751b6b0056984
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338042"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="ec4a7-102">Пользовательские составные конструкторы - средство представления элементов рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ec4a7-102">Custom Composite Designers - Workflow Item Presenter</span></span>

<span data-ttu-id="ec4a7-103"><xref:System.Activities.Presentation.WorkflowItemPresenter> — это тип ключа в модели программирования конструктора WF, который позволяет создавать "Drop Zone", где можно разместить произвольное действие.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="ec4a7-104">В этом образце показано, как создать конструктор действий, который охватывает такую "область перетаскивания".</span><span class="sxs-lookup"><span data-stu-id="ec4a7-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

<span data-ttu-id="ec4a7-105">В этом образце показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-105">This sample demonstrates:</span></span>

- <span data-ttu-id="ec4a7-106">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="ec4a7-107">Регистрация пользовательского конструктора с использованием хранилища метаданных.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-107">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="ec4a7-108">Программирование повторно размещенной области элементов декларативно и принудительно.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-108">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="ec4a7-109">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="ec4a7-109">Sample Details</span></span>

<span data-ttu-id="ec4a7-110">Код для этого образца показывает следующее:</span><span class="sxs-lookup"><span data-stu-id="ec4a7-110">The code for this sample shows:</span></span>

- <span data-ttu-id="ec4a7-111">Для класса `SimpleNativeActivity` создается конструктор пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-111">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="ec4a7-112">Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-112">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="ec4a7-113">Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Body`.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-113">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="ec4a7-114">`ModelItem` — это свойство для <xref:System.Activities.Presentation.ActivityDesigner>, которое ссылается на базовый объект, для которого используется конструктор, в данном случае **симпленативеактивити**.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-114">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="ec4a7-115">Настройка, сборка и запуск примера</span><span class="sxs-lookup"><span data-stu-id="ec4a7-115">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="ec4a7-116">Откройте решение в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-116">Open the solution in Visual Studio.</span></span>

2. <span data-ttu-id="ec4a7-117">Нажмите клавишу **F5** , чтобы скомпилировать и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-117">Press **F5** to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec4a7-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ec4a7-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ec4a7-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ec4a7-120">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec4a7-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ec4a7-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a><span data-ttu-id="ec4a7-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec4a7-122">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="ec4a7-123">Разработка приложений с помощью конструктора рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ec4a7-123">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
