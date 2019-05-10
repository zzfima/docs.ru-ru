---
title: Задача 2. Размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: cce90c6b7f5edfaf960415f0a5d0787f8eee526b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665289"
---
# <a name="task-2-host-the-workflow-designer"></a>Задача 2. Размещение конструктора рабочих процессов
В этом разделе описывается процедура по размещению экземпляра [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] в приложении Windows Presentation Foundation (WPF).  
  
 Процедура выполняет настройку **сетки** элемент управления, который содержит конструктор, программным образом создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner> , содержащий значение по умолчанию <xref:System.Activities.Statements.Sequence> действия, регистрирует метаданные конструктора, чтобы предоставить Поддержка конструктора для всех встроенных действий и узлы [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] приложения.  
  
### <a name="to-host-the-workflow-designer"></a>Размещение конструктора рабочих процессов  
  
1. Откройте проект HostingApplication, созданный в [задаче 1: Создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).  
  
2. Отрегулируйте размер окна, чтобы было проще использовать [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Чтобы сделать это, выберите **MainWindow** в конструкторе, нажмите клавишу F4, чтобы открыть **свойства** окно и в **макета** раздел существует, задайте **ширины** значению, равному 600 и **высота** значение 350.  
  
3. Задайте имя сетки, выбрав **сетки** панель в конструкторе (щелкните поле в **MainWindow**) и параметр **имя** свойство в верхней части  **Свойства** окно, чтобы значение «grid1».  
  
4. В **свойства** окно, нажмите кнопку с многоточием (**...** ) рядом с полем `ColumnDefinitions` свойства, чтобы открыть **редактор коллекции** диалоговое окно.  
  
5. В **редактор коллекции** диалоговом окне щелкните **добавить** кнопку три раза, чтобы вставить в макет три столбца. Первый столбец будет содержать **элементов**, во втором столбце будет размещаться [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], и третий столбец будет использоваться для инспектора свойств.  
  
6. Задайте `Width` свойство среднего столбца значение «4 *».  
  
7. Нажмите кнопку **ОК** , чтобы сохранить изменения. Следующий код XAML будет добавлен в файл MainWindows.xaml.  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. В **обозревателе решений**, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**. Измените код, выполнив следующие шаги.  
  
    1. Добавьте следующие пространства имен.  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2. Чтобы объявить закрытый член класса для хранения экземпляра <xref:System.Activities.Presentation.WorkflowDesigner>, добавьте в класс `MainWindow` следующий код.  
  
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
  
    3. Добавьте следующий метод `AddDesigner` в класс `MainWindow`. Эта реализация создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, добавляет <xref:System.Activities.Statements.Sequence> действия и помещает его в средний столбец grid1 **сетки**.  
  
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
  
    4. Зарегистрируйте метаданные конструктора, чтобы добавить поддержку конструктора для всех встроенных действий. Это позволяет перетаскивать действия из области элементов в исходное действие <xref:System.Activities.Statements.Sequence> в [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Для этого добавьте метод `RegisterMetadata` в класс `MainWindow`.  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         Дополнительные сведения о регистрации конструкторов действий см. в разделе [как: Создание пользовательского конструктора действий](how-to-create-a-custom-activity-designer.md).  
  
    5. В конструкторе класса `MainWindow` добавьте вызовы объявленных ранее методов для регистрации метаданных для поддержки конструктора и создания <xref:System.Activities.Presentation.WorkflowDesigner>.  
  
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
        >  Метод `RegisterMetadata` регистрирует метаданные конструктора встроенных действий, включая действие <xref:System.Activities.Statements.Sequence>. Поскольку метод `AddDesigner` использует действие <xref:System.Activities.Statements.Sequence>, сначала необходимо вызвать метод `RegisterMetadata`.  
  
9. Нажмите клавишу F5 для построения и выполнения решения.  
  
10. См. в разделе [задача 3: Создание элементов и сетки свойств](task-3-create-the-toolbox-and-propertygrid-panes.md) вы научитесь добавлять **элементов** и **PropertyGrid** поддержки в повторно размещенном рабочего процесса конструктор.  
  
## <a name="see-also"></a>См. также

- [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Упражнение 1. Создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Задача 3. Создание элементов и сетки свойств](task-3-create-the-toolbox-and-propertygrid-panes.md)
