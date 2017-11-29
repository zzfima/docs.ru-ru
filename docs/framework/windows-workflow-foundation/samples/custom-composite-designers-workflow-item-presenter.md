---
title: "Пользовательские составные конструкторы - средство представления элементов рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3fa40a7a864ae65d15d787f5dec58a8da7b8e9a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Пользовательские составные конструкторы - средство представления элементов рабочего процесса
<xref:System.Activities.Presentation.WorkflowItemPresenter> Является ключевым типом в модели программирования конструктора WF, позволяющей создавать «зону сброса» где могут размещаться произвольные действия. В этом примере показано, как построить конструктор действий, который предоставляет доступ к «зону перетаскивания.»  
  
 В этом образце показаны следующие действия.  
  
## <a name="demonstrates"></a>Демонстрации  
  
-   Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
-   Регистрация пользовательского конструктора с использованием хранилища метаданных.  
  
-   Программирование повторно размещенной области элементов декларативно и принудительно.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Код для этого образца показывает следующее:  
  
-   Для класса `SimpleNativeActivity` создается конструктор пользовательских действий.  
  
-   Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
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
  
 Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Body`. `ModelItem`-Свойство <xref:System.Activities.Presentation.ActivityDesigner> , относится к базовому объекту, в которой используется конструктор, в этом случае **SimpleNativeActivity**.  
  
#### <a name="to-setup-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы скомпилировать и запустить приложение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [Разработка приложений с помощью конструктора рабочего процесса](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
