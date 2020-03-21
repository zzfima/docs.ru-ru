---
title: Повторное размещение конструктора
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: b72e3450799db40988c8b99e4db3707de330d8ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182821"
---
# <a name="designer-rehosting"></a>Повторное размещение конструктора
Повторное размещение конструктора представляет собой обычный сценарий, предусматривающий размещение поля визуальной разработки рабочего процесса в пользовательском приложении. Наиболее привычным приложением размещения является Visual Studio, однако в целом ряде сценариев может быть полезным отображение конструктора рабочих процессов в приложении.  
  
- Наблюдение за приложениями (позволяющее конечному пользователю визуально представить процесс, а также данные среды выполнения о процессе, такие как состояние, активное в настоящее время, агрегированные данные времени выполнения или другие сведения об экземпляре рабочего процесса).  
  
- Приложения, которые позволяют пользователю настраивать процесс с ограниченным набором действий.  
  
 Для поддержки этих типов приложений в составе платформы .NET Framework поставляется конструктор рабочих процессов, который может быть размещен в приложении WPF или в приложении WinForms с соответствующим кодом размещения WPF. В этом примере демонстрируются следующее:  
  
- Повторное размещение конструктора рабочих процессов.  
  
- Кроме того, использование повторно размещенной области элементов и таблицы свойств.  
  
## <a name="rehosting-the-designer"></a>Повторное размещение конструктора  
 Этот образец показывает, как создать макет WPF, содержащий конструктор, который можно видеть в следующем макете таблицы (код панели инструментов опущен в целях экономии места). Обратите внимание на то, как именуются границы, которые содержат конструктор и таблицы свойств.  
  
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
  
 Затем в образце создается конструктор и связываются его первичные представления <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> и <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> с соответствующим контейнером в пользовательском интерфейсе. В следующем примере есть несколько дополнительных строк кода, которые заслуживают более подробного объяснения. Вызов <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> необходим для ассоциировать конструкторов активности по умолчанию для действий, поставляемых с помощью .NET Framework. <xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> вызывается для передачи элемента WF, подлежащего редактированию. Наконец, в область пользовательского интерфейса помещаются <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (первичное полотно) и <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (таблица свойств).  
  
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
  
## <a name="using-the-rehosted-toolbox"></a>Использование повторно размещенной области инструментов  
 В этом образце используется повторно размещенный элемент управления области инструментов декларативно в XAML. Обратите внимание на то, что в коде каждый может передать некоторый тип в конструктор <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.  
  
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
  
#### <a name="using-the-sample"></a>Использование образца  
  
1. Откройте решение DesignerRehosting.sln в Visual Studio 2010.  
  
2. Чтобы скомпилировать и запустить приложение, нажмите клавишу F5.  
  
3. Приложение WPF начинается с повторно размещенного конструктора.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`
