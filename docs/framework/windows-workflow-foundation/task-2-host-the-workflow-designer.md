---
title: Задача 2. Размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 92c5fa347cc7a2c0088ab8f4fbdfddf25ffb83c1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037859"
---
# <a name="task-2-host-the-workflow-designer"></a>Задача 2. Размещение конструктора рабочих процессов

В этом разделе описывается процедура размещения экземпляра [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] в приложении Windows Presentation Foundation (WPF).

Процедура настраивает элемент управления **Grid** , содержащий конструктор, программно создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner> , содержащий действие по умолчанию <xref:System.Activities.Statements.Sequence> , регистрирует метаданные конструктора для обеспечения поддержки конструктора для всех встроенные действия и размещаются [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в приложении WPF.

### <a name="to-host-the-workflow-designer"></a>Размещение конструктора рабочих процессов

1. Откройте проект хостингаппликатион, созданный в [задаче 1. Создайте новое приложение](task-1-create-a-new-wpf-app.md)Windows Presentation Foundation.

2. Отрегулируйте размер окна, чтобы было проще использовать [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Для этого выберите **MainWindow** в конструкторе, нажмите клавишу F4, чтобы открыть окно **свойства** , и в разделе **макет** установите для **ширины** значение 600, а для **высоты** — значение 350.

3. Задайте имя сетки, выбрав Панель **сетки** в конструкторе (щелкните поле в **MainWindow**) и задайте для свойства **Name** в верхней части окна **Свойства** значение "grid1".

4. В окне **Свойства** нажмите кнопку с многоточием ( **...** ) `ColumnDefinitions` рядом со свойством, чтобы открыть диалоговое окно **Редактор коллекции** .

5. В диалоговом окне **Редактор коллекций** нажмите кнопку **Добавить** три раза, чтобы вставить три столбца в макет. Первый столбец будет содержать **область элементов**, второй столбец будет размещать [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], а третий столбец будет использоваться для инспектора свойств.

6. Задайте для `Width` свойства среднего столбца значение 4 *.

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

8. В **Обозреватель решений**щелкните правой кнопкой мыши файл MainWindow. XAML и выберите **Просмотреть код**. Измените код, выполнив следующие шаги.

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

    3. Добавьте следующий метод `AddDesigner` в класс `MainWindow`. Реализация создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, <xref:System.Activities.Statements.Sequence> добавляет к нему действие и помещает его в средний столбец **сетки**grid1.

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

        Дополнительные сведения о регистрации конструкторов действий см. [в разделе как Создайте пользовательский конструктор](how-to-create-a-custom-activity-designer.md)действий.

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
        > Метод `RegisterMetadata` регистрирует метаданные конструктора встроенных действий, включая действие <xref:System.Activities.Statements.Sequence>. Поскольку метод `AddDesigner` использует действие <xref:System.Activities.Statements.Sequence>, сначала необходимо вызвать метод `RegisterMetadata`.

9. Нажмите клавишу F5 для построения и выполнения решения.

10. См [. задачу 3. Создайте панели элементов и PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) , чтобы узнать, как добавить **панель элементов** и поддержку **PropertyGrid** в переразмещенный конструктор рабочих процессов.

## <a name="see-also"></a>См. также

- [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Задача 1. Создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Задача 3. Создание панели элементов и панелей PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md)
