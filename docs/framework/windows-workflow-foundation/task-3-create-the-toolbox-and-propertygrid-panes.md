---
title: Задача 3. Создание области элементов и сетки свойств
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 45819577c39185a5d95da81521cd541087a64efc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721230"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Задача 3. Создание области элементов и сетки свойств
В этой задаче вы создадите **элементов** и **PropertyGrid** областей и добавлять их в повторно размещенном [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Для ссылки, код, который должен содержаться в файле MainWindow.xaml.cs после выполнения трех задач в [повторное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md) ряд разделов указан в конце этого раздела.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Создание области элементов и ее добавление к сетке.  
  
1.  Откройте проект HostingApplication, полученный с помощью процедуры, описанной в [задаче 2: Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md).  
  
2.  В **обозревателе решений** панели, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**.  
  
3.  Добавить `GetToolboxControl` метод `MainWindow` класс, который создает <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, добавляет новую **элементов** категорию, чтобы **элементов**и назначает <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence> типы действий к этой категории.  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4.  Добавьте закрытый `AddToolbox` метод `MainWindow` класс, который помещает **элементов** в левом столбце сетки.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  Добавьте вызов метода `AddToolBox` в конструктор класса `MainWindow()`, как показано в следующем коде.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  Нажмите клавишу F5, чтобы построить и выполнить решение. **Элементов** содержащий <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence> действия должны отображаться.  
  
### <a name="to-create-the-propertygrid"></a>Создание области PropertyGrid  
  
1.  В **обозревателе решений** панели, щелкните правой кнопкой мыши файл MainWindow.xaml и выберите **Просмотр кода**.  
  
2.  Добавить `AddPropertyInspector` метод `MainWindow` класса для размещения **PropertyGrid** области в самом правом столбце сетки.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  Добавьте вызов метода `AddPropertyInspector` в конструктор класса `MainWindow()`, как показано в следующем коде.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
    ```  
  
4.  Нажмите клавишу F5 для построения и выполнения решения. **Элементов**, визуальной разработки рабочего процесса, и **PropertyGrid** области должны отображаться, а при перетаскивании <xref:System.Activities.Statements.Assign> действия или <xref:System.Activities.Statements.Sequence> действия на холст конструктора Сетка свойств должна обновиться в зависимости от выделенного действия.  
  
## <a name="example"></a>Пример  
 Теперь файл MainWindow.xaml.cs должен содержать следующий код.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
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
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>См. также
- [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Упражнение 1. Создание нового приложения Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Задача 2. Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md)
