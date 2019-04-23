---
title: Повторное размещение конструктора
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: b2a51014e34bf27d6f016db71d2c2eaabb906c6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328170"
---
# <a name="designer-rehosting"></a><span data-ttu-id="35354-102">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="35354-102">Designer Rehosting</span></span>
<span data-ttu-id="35354-103">Повторное размещение конструктора представляет собой обычный сценарий, предусматривающий размещение поля визуальной разработки рабочего процесса в пользовательском приложении.</span><span class="sxs-lookup"><span data-stu-id="35354-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="35354-104">Наиболее привычным приложением размещения является Visual Studio, однако в целом ряде сценариев может быть полезным отображение конструктора рабочих процессов в приложении.</span><span class="sxs-lookup"><span data-stu-id="35354-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
-   <span data-ttu-id="35354-105">Наблюдение за приложениями (позволяющее конечному пользователю визуально представить процесс, а также данные среды выполнения о процессе, такие как состояние, активное в настоящее время, агрегированные данные времени выполнения или другие сведения об экземпляре рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="35354-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
-   <span data-ttu-id="35354-106">Приложения, которые позволяют пользователю настраивать процесс с ограниченным набором действий.</span><span class="sxs-lookup"><span data-stu-id="35354-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="35354-107">Для поддержки этих типов приложений в составе платформы .NET Framework поставляется конструктор рабочих процессов, который может быть размещен в приложении WPF или в приложении WinForms с соответствующим кодом размещения WPF.</span><span class="sxs-lookup"><span data-stu-id="35354-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="35354-108">В этом образце показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="35354-108">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="35354-109">Повторное размещение конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="35354-109">Rehosting the WF designer.</span></span>  
  
-   <span data-ttu-id="35354-110">Кроме того, использование повторно размещенной области элементов и таблицы свойств.</span><span class="sxs-lookup"><span data-stu-id="35354-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="35354-111">Повторное размещение конструктора</span><span class="sxs-lookup"><span data-stu-id="35354-111">Rehosting the designer</span></span>  
 <span data-ttu-id="35354-112">Этот образец показывает, как создать макет WPF, содержащий конструктор, который можно видеть в следующем макете таблицы (код панели инструментов опущен в целях экономии места).</span><span class="sxs-lookup"><span data-stu-id="35354-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="35354-113">Обратите внимание на то, как именуются границы, которые содержат конструктор и таблицы свойств.</span><span class="sxs-lookup"><span data-stu-id="35354-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="35354-114">Затем в образце создается конструктор и связываются его первичные представления <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> и <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> с соответствующим контейнером в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="35354-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="35354-115">В следующем примере есть несколько дополнительных строк кода, которые заслуживают более подробного объяснения.</span><span class="sxs-lookup"><span data-stu-id="35354-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="35354-116">Вызов <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> необходим для связи конструкторов действий по умолчанию для действий, поставляемых с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35354-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="35354-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> вызывается для передачи элемента WF, подлежащего редактированию.</span><span class="sxs-lookup"><span data-stu-id="35354-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="35354-118">Наконец, в область пользовательского интерфейса помещаются <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (первичное полотно) и <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (таблица свойств).</span><span class="sxs-lookup"><span data-stu-id="35354-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="35354-119">Использование повторно размещенной области инструментов</span><span class="sxs-lookup"><span data-stu-id="35354-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="35354-120">В этом образце используется повторно размещенный элемент управления области инструментов декларативно в XAML.</span><span class="sxs-lookup"><span data-stu-id="35354-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="35354-121">Обратите внимание на то, что в коде каждый может передать некоторый тип в конструктор <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.</span><span class="sxs-lookup"><span data-stu-id="35354-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
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
            <sapt:ToolboxControl>  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="35354-122">Использование образца</span><span class="sxs-lookup"><span data-stu-id="35354-122">Using the sample</span></span>  
  
1. <span data-ttu-id="35354-123">Откройте решение DesignerRehosting.sln в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="35354-123">Open the DesignerRehosting.sln solution in Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="35354-124">Чтобы скомпилировать и запустить приложение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="35354-124">Press F5 to compile and run the application.</span></span>  
  
3. <span data-ttu-id="35354-125">Приложение WPF начинается с повторно размещенного конструктора.</span><span class="sxs-lookup"><span data-stu-id="35354-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35354-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="35354-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35354-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="35354-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35354-128">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="35354-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35354-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="35354-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`