---
title: "Пользовательские составные конструкторы — средство представления элементов рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Пользовательские составные конструкторы — средство представления элементов рабочего процесса
<xref:System.Activities.Design.WorkflowItemsPresenter> является типом ключа в модели программирования конструктора WF, позволяющим редактирование коллекции содержащихся элементов.В этом образце показано, как построить конструктор действий, который предоставляет доступ к такой изменяемой коллекции.  
  
 В этом образце показаны следующие действия.  
  
-   Создание настраиваемого конструктора действий с <xref:System.Activities.Design.WorkflowItemsPresenter>.  
  
-   Создание конструктора действий со «свернутым» и «восстановленным» представлением.  
  
-   Переопределение конструктора по умолчанию в повторно размещенном приложении.  
  
### Настройка, построение и выполнение образца  
  
1.  Откройте решение **UsingWorkflowItemsPresenter.sln** образца для C\# или для VB в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.Должно открыться повторно размещенное приложение конструктора рабочих процессов, после чего действия можно перетащить на полотно.  
  
## Описание образца  
 Код для этого образца показывает следующее.  
  
-   Действие, для которого построен конструктор: `Parallel`  
  
-   Создание настраиваемого конструктора действий с <xref:System.Activities.Design.WorkflowItemsPresenter>.Некоторые замечания.  
  
    -   Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Branches`.`ModelItem` — свойство <xref:System.Activities.Design.WorkflowElementDesigner>, которое относится к базовому объекту, для которого используется конструктор, в данном случае — `Parallel`.  
  
    -   Шаблон <xref:System.Activities.Design.WorkflowItemsPresenter.SpacerTemplate%2A> может использоваться для указания видимого изображения, отображаемого между отдельными элементами коллекции.  
  
    -   <xref:System.Activities.Design.WorkflowItemsPresenter.ItemsPanel%2A> является шаблоном, который может быть предоставлен для определения макета элементов в коллекции.В данном случае используется горизонтальный элемент StackPanel.  
  
 Это показано в следующем примере кода.  
  
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
  
-   Выполнение сопоставление объекта `DesignerAttribute` с типом `Parallel`, а затем вывод указанных атрибутов.  
  
    -   Сначала зарегистрируйте все конструкторы по умолчанию.  
  
 Ниже приведен пример кода.  
  
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
  
-   -   Далее переопределите параллель в методе `RegisterCustomMetadata`.  
  
 В следующем коде это показано на языках C\# и Visual Basic.  
  
 C\#  
  
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
  
-   Наконец, обратите внимание на использование различных шаблонов данных и триггеров для выбора соответствующего шаблона на основании свойства `IsRootDesigner`.  
  
 Ниже приведен пример кода.  
  
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
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## См. также  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>   
 [Разработка приложений с помощью конструктора рабочего процесса](../Topic/Developing%20Applications%20with%20the%20Workflow%20Designer.md)