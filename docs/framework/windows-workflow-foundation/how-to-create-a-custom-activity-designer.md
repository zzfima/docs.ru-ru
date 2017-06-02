---
title: "Как создать настраиваемый конструктор действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Как создать настраиваемый конструктор действий
Пользовательские конструкторы действий обычно реализуются таким образом, что их связанные действия сочетаются с другими действиями, конструкторы которых могут помещаться вместе с ними на область конструктора.Эта функциональность требует, чтобы пользовательский конструктор действий предоставлял «зону перетаскивания», в которую может быть помещено произвольное действие, а также средства для управления результирующей коллекцией элементов в области конструктора.В этом разделе описано создание пользовательского конструктора действий, содержащего «зону перетаскивания», а также создание пользовательского конструктора действий, предоставляющего функции редактирования, необходимые для управления коллекцией элементов конструктора.  
  
 Пользовательские конструкторы действий обычно наследуют от <xref:System.Activities.Presentation.ActivityDesigner>, который является базовым типом конструктора действий по умолчанию для любых действий без определенного конструктора.Этот тип обеспечивает взаимодействие с таблицей свойств во время разработки и настройку основных аспектов, например, управления цветами и значками.  
  
 Для упрощения разработки пользовательских конструкторов действий в конструкторе <xref:System.Activities.Presentation.ActivityDesigner> используют два элемента управления помощника, <xref:System.Activities.Presentation.WorkflowItemPresenter> и <xref:System.Activities.Presentation.WorkflowItemsPresenter>.Они обрабатывают общие функции, например перетаскивание дочерних элементов, удаление, выделение и добавление этих дочерних элементов.<xref:System.Activities.Presentation.WorkflowItemPresenter> может содержать один дочерний элемент пользовательского интерфейса, предоставляя «зону перетаскивания», а <xref:System.Activities.Presentation.WorkflowItemsPresenter> поддерживает несколько элементов пользовательского интерфейса, в том числе такие дополнительные функции, как упорядочение, перемещение, удаление и добавление дочерних элементов.  
  
 Другая важная часть описания, которую необходимо выделить в реализации пользовательских конструкторов действий, относится к способу привязывания визуальных изменений с использованием привязки данных [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] к хранящемуся в памяти экземпляру объекта, который изменяется в конструкторе.Это достигается с помощью дерева элементов модели, которое также обеспечивает уведомления об изменениях и отслеживание таких событий, как изменения состояний.  
  
 В данном подразделе описаны две процедуры.  
  
1.  Первая процедура описывает создание пользовательских конструкторов действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>, предоставляющим «зону перетаскивания», в которую можно помещать другие действия.Эта процедура основана на образце [Пользовательские составные конструкторы — средство представления элементов рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md).  
  
2.  Вторая процедура описывает создание пользовательских конструкторов действий с элементом управления помощника <xref:System.Activities.Presentation.WorkflowItemsPresenter>, предоставляющим функции, необходимые для изменения коллекции содержащихся в нем элементов.Эта процедура основана на образце [Пользовательские составные конструкторы — средство представления элементов рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md).  
  
### Создание пользовательского конструктора действий с «зоной перетаскивания» с использованием WorkflowItemPresenter  
  
1.  Запустите среду [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  В меню **Файл** укажите пункт **Создать** и выберите пункт **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  В области **Установленные шаблоны** выберите **Windows** в категории предпочтительного языка.  
  
4.  В области **Шаблоны** выберите пункт **Приложение WPF**.  
  
5.  В поле **Имя** введите `UsingWorkflowItemPresenter`.  
  
6.  В поле **Расположение** введите путь к папке, где будет сохранен проект, или нажмите кнопку **Обзор**, чтобы перейти в эту папку.  
  
7.  В поле **Решение** примите значение по умолчанию.  
  
8.  Нажмите кнопку **ОК**.  
  
9. В **обозревателе решений** щелкните правой кнопкой мыши файл MainWindows.xaml, выберите команду **Удалить** и нажмите кнопку **ОК** для подтверждения в диалоговом окне **Microsoft Visual Studio**.  
  
10. Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в окне **Обозреватель решений**, выберите команду **Добавить** и пункт **Новый элемент…**, чтобы открыть диалоговое окно **Добавление нового элемента**, затем выберите категорию **WPF** из раздела **Установленные шаблоны** в левой части окна.  
  
11. Выберите шаблон **Window \(WPF\)**, назовите его `RehostingWFDesigner` и нажмите кнопку **Добавить**.  
  
12. Откройте файл RehostingWFDesigner.xaml file и вставьте в него следующий код, чтобы определить пользовательский интерфейс для приложения.  
  
    ```  
  
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
  
13. Чтобы связать конструктор действия с типом действия, необходимо зарегистрировать конструктор действия в хранилище метаданных.Для этого добавьте метод `RegisterMetadata` в класс `RehostingWFDesigner`.В области метода `RegisterMetadata` создайте объект <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> и вызовите метод <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>, чтобы добавить к нему атрибуты.Вызовите метод <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>, чтобы добавить <xref:System.Activities.Presentation.Metadata.AttributeTable> в хранилище метаданных.Следующий код содержит логику повторного размещения для конструктора.Он регистрирует метаданные, помещает действие `SimpleNativeActivity` в область элементов и создает рабочий процесс.Поместите этот код в файл RehostingWFDesigner.xaml.cs.  
  
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
  
14. Щелкните правой кнопкой мыши папку References в «Обозревателе решений» и выберите **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.  
  
15. На вкладке **.NET** найдите сборку **System.Activities.Core.Presentation**, выберите ее и нажмите кнопку **ОК**.  
  
16. Таким же образом добавьте ссылки на следующие сборки:  
  
    1.  System.Data.DataSetExtensions.dll  
  
    2.  System.Activities.Presentation.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
17. Откройте файл App.xaml file и измените значение StartUpUri на «RehostingWFDesigner.xaml».  
  
18. Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в окне **Обозреватель решений**, выберите команду **Добавить** и пункт **Новый элемент…**, чтобы открыть диалоговое окно **Добавление нового элемента**, и выберите категорию **Рабочий процесс** в разделе **Установленные шаблоны** слева.  
  
19. Выберите шаблон **Activity Designer**, назовите его `SimpleNativeDesigner` и нажмите кнопку **Добавить**.  
  
20. Откройте файл SimpleNativeDesigner.xaml и вставьте в него следующий код.Обратите внимание, что этот код использует <xref:System.Activities.Presentation.ActivityDesigner> в качестве корневого элемента и показывает, как привязка используется для интеграции <xref:System.Activities.Presentation.WorkflowItemPresenter> в конструктор, чтобы дочерний тип можно было отобразить в конструкторе составных действий.  
  
    > [!NOTE]
    >  Схема для <xref:System.Activities.Presentation.ActivityDesigner> позволяет добавлять только один дочерний элемент в определение пользовательского конструктора действий. Однако этим элементом может быть `StackPanel`, `Grid` или другой составной элемент пользовательского интерфейса.  
  
    ```  
  
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
  
21. Щелкните правой кнопкой мыши проект UsingWorkflowItemPresenter в окне **Обозреватель решений**, выберите команду **Добавить** и пункт **Новый элемент…**, чтобы открыть диалоговое окно **Добавление нового элемента**, и выберите категорию **Рабочий процесс** в разделе **Установленные шаблоны** слева.  
  
22. Выберите шаблон **Code Activity**, назовите его `SimpleNativeActivity` и нажмите кнопку **Добавить**.  
  
23. Реализуйте класс `SimpleNativeActivity`, введя следующий код в файл SimpleNativeActivity.cs.  
  
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
  
24. В меню **Построить** выберите пункт **Построить решение**.  
  
25. В меню **Отладка** выберите команду **Запуск без отладки**, чтобы открыть повторно размещенное пользовательское окно конструктора.  
  
### Создание пользовательского конструктора действий с использованием WorkflowItemsPresenter  
  
1.  Процедура для второго пользовательского конструктора действий похожа на предыдущую с определенными изменениями, первое из которых заключается в присвоении второму приложению имени `UsingWorkflowItemsPresenter`.Кроме того, это приложение не определяет новое пользовательское действие.  
  
2.  Основные различия находятся в файлах CustomParallelDesigner.xaml и RehostingWFDesigner.xaml.cs.Ниже приводится код из файла CustomParallelDesigne.xaml, который определяет пользовательский интерфейс.  
  
    ```  
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
  
3.  Ниже приводится код из файла RehostingWFDesigner.xaml.cs, который предоставляет логику повторного размещения.  
  
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
  
## См. также  
 <xref:System.Activities.Presentation.ActivityDesigner>   
 <xref:System.Activities.Presentation.WorkflowItemPresenter>   
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>   
 <xref:System.Activities.Presentation.WorkflowViewElement>   
 <xref:System.Activities.Presentation.Model.ModelItem>   
 [Рекомендации по настройке конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)