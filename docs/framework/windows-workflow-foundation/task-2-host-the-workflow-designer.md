---
title: "Задание 2. Размещение конструктора рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Задание 2. Размещение конструктора рабочих процессов
В этом разделе описана процедура по размещению экземпляра [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] в приложении [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].  
  
 Процедура выполняет настройку элемента управления **Сетка**, который содержит конструктор, программным образом создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, который содержит действие <xref:System.Activities.Statements.Sequence> по умолчанию, регистрирует метаданные конструктора, чтобы обеспечить поддержку конструктора для всех встроенных действий, и размещает [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в приложении [!INCLUDE[avalon2](../../../includes/avalon2-md.md)].  
  
### Размещение конструктора рабочих процессов  
  
1.  Откройте проект HostingApplication, созданный в разделе [Задание 1. Создание нового приложения Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md).  
  
2.  Отрегулируйте размер окна, чтобы было проще использовать [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].Для этого выберите в конструкторе окно **MainWindow**, нажмите клавишу F4, чтобы открыть окно**Свойства**, и в разделе **Макет** установите свойство **Ширина** в значение 600, а свойство **Высота** — в значение 350.  
  
3.  Задайте имя сетки, выбрав панель **Сетка** в конструкторе \(щелкните поле в окне **MainWindow**\) и установив свойство **Имя** в верхней части окна **Свойства** в значение grid1.  
  
4.  В окне **Свойства** нажмите кнопку с многоточием \(**…**\) рядом со свойством `ColumnDefinitions`, чтобы открыть диалоговое окно **Редактор коллекции**.  
  
5.  В диалоговом окне **Редактор коллекции** три раза нажмите кнопку **Добавить**, чтобы вставить в макет три столбца.Первый столбец будет содержать **Область элементов**, во втором столбце будет размещен объект [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], и третий столбец будет использован для инспектора свойств.  
  
6.  Свойству `Width` среднего столбца задайте значение «4\*».  
  
7.  Нажмите кнопку **ОК** для сохранения изменений.Следующий код XAML будет добавлен в файл MainWindows.xaml.  
  
    ```  
  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
  
    ```  
  
8.  В **обозревателе решений** щелкните правой кнопкой мыши файл MainWindow.xaml и выберите команду **Просмотреть код**.Измените код, выполнив следующие шаги.  
  
    1.  Добавьте следующие пространства имен.  
  
        ```csharp  
  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
  
        ```  
  
    2.  Чтобы объявить закрытый член класса для хранения экземпляра <xref:System.Activities.Presentation.WorkflowDesigner>, добавьте в класс `MainWindow` следующий код.  
  
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
  
    3.  Добавьте следующий метод `AddDesigner` в класс `MainWindow`.В реализации создается экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, затем в него добавляется действие <xref:System.Activities.Statements.Sequence>, и экземпляр помещается в средний столбец **сетки** grid1.  
  
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
  
    4.  Зарегистрируйте метаданные конструктора, чтобы добавить поддержку конструктора для всех встроенных действий.Это позволяет перетаскивать действия из области элементов в исходное действие <xref:System.Activities.Statements.Sequence> в [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].Для этого добавьте метод `RegisterMetadata` в класс `MainWindow`.  
  
        ```csharp  
  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)] регистрации конструкторов действий см. в разделе [Как создать настраиваемый конструктор действий](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-activity-designer.md).  
  
    5.  В конструкторе класса `MainWindow` добавьте вызовы объявленных ранее методов для регистрации метаданных для поддержки конструктора и создания <xref:System.Activities.Presentation.WorkflowDesigner>.  
  
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
        >  Метод `RegisterMetadata` регистрирует метаданные конструктора встроенных действий, включая действие <xref:System.Activities.Statements.Sequence>.Поскольку метод `AddDesigner` использует действие <xref:System.Activities.Statements.Sequence>, сначала необходимо вызвать метод `RegisterMetadata`.  
  
9. Нажмите клавишу F5 для построения и выполнения решения.  
  
10. Инструкции по добавлению поддержки **Области элементов** и **PropertyGrid** для вновь размещенного конструктора рабочих процессов см. в разделе [Задание 3. Создание области элементов и сетки свойств](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md).  
  
## См. также  
 [Повторное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Задание 1. Создание нового приложения Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Задание 3. Создание области элементов и сетки свойств](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md)