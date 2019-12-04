---
title: Задача 2. Размещение конструктора рабочих процессов
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8e4c17ed182cec7748b9a1f11f76ff90aa60c39e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715780"
---
# <a name="task-2-host-the-workflow-designer"></a>Задача 2. Размещение конструктора рабочих процессов

В этом разделе описывается процедура размещения экземпляра конструктор рабочих процессов Windows в приложении Windows Presentation Foundation (WPF).

Процедура настраивает элемент управления **Grid** , содержащий конструктор, программно создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, содержащий действие <xref:System.Activities.Statements.Sequence> по умолчанию, регистрирует метаданные конструктора для обеспечения поддержки конструктора для всех встроенных действий и размещает конструктор рабочих процессов в приложении WPF.

## <a name="to-host-the-workflow-designer"></a>Размещение конструктора рабочих процессов

1. Откройте проект Хостингаппликатион, созданный в [задаче 1: создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).

2. Измените размер окна, чтобы упростить использование конструктор рабочих процессов. Для этого выберите **MainWindow** в конструкторе, нажмите клавишу F4, чтобы открыть окно **свойства** , и в разделе **макет** установите для **ширины** значение 600, а для **высоты** — значение 350.

3. Задайте имя сетки, выбрав Панель **сетки** в конструкторе (щелкните поле в **MainWindow**) и задайте для свойства **Name** в верхней части окна **Свойства** значение "grid1".

4. В окне **Свойства** нажмите кнопку с многоточием ( **...** ) рядом со свойством `ColumnDefinitions`, чтобы открыть диалоговое окно **Редактор коллекции** .

5. В диалоговом окне **Редактор коллекций** нажмите кнопку **Добавить** три раза, чтобы вставить три столбца в макет. Первый столбец будет содержать **область элементов**, второй столбец будет размещать конструктор рабочих процессов, а третий столбец будет использоваться для инспектора свойств.

6. Задайте для свойства `Width` среднего столбца значение 4 *.

7. Нажмите кнопку **ОК** , чтобы сохранить изменения. В файл *MainWindow. XAML* добавляется следующий код XAML:

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. В **Обозреватель решений**щелкните правой кнопкой мыши файл *MainWindow. XAML* и выберите **Просмотреть код**. Измените код, выполнив следующие шаги.

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

    2. Чтобы объявить поле закрытого члена для хранения экземпляра <xref:System.Activities.Presentation.WorkflowDesigner>, добавьте следующий код в класс `MainWindow`:

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

    3. Добавьте следующий метод `AddDesigner` в класс `MainWindow`. Реализация создает экземпляр <xref:System.Activities.Presentation.WorkflowDesigner>, добавляет к нему действие <xref:System.Activities.Statements.Sequence> и помещает его в среднюю колонку **сетки**grid1.

        ```csharp
        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. Зарегистрируйте метаданные конструктора, чтобы добавить поддержку конструктора для всех встроенных действий. Это позволяет удалять действия из панели элементов на исходное <xref:System.Activities.Statements.Sequence> действие в конструктор рабочих процессов. Для этого добавьте метод `RegisterMetadata` в класс `MainWindow`.

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        Дополнительные сведения о регистрации конструкторов действий см. [в разделе инструкции. Создание пользовательского конструктора действий](how-to-create-a-custom-activity-designer.md).

    5. В конструкторе класса `MainWindow` добавьте вызовы объявленных ранее методов для регистрации метаданных для поддержки конструктора и создания <xref:System.Activities.Presentation.WorkflowDesigner>.

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > Метод `RegisterMetadata` регистрирует метаданные конструктора встроенных действий, включая действие <xref:System.Activities.Statements.Sequence>. Поскольку метод `AddDesigner` использует действие <xref:System.Activities.Statements.Sequence>, сначала необходимо вызвать метод `RegisterMetadata`.

9. Нажмите клавишу <kbd>F5</kbd> , чтобы создать и запустить решение.

10. См. раздел [Задача 3. Создание панелей элементов и PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) , чтобы узнать, как добавить **панель элементов** и поддержку **PropertyGrid** в переразмещенный конструктор рабочих процессов.

## <a name="see-also"></a>См. также:

- [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Задача 1. Создание приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Задача 3. Создание панели элементов и сетки свойств](task-3-create-the-toolbox-and-propertygrid-panes.md)
