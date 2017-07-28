---
title: "Задание 3. Создание области элементов и сетки свойств | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Задание 3. Создание области элементов и сетки свойств
В этой задаче создаются области элементов **Toolbox** и **PropertyGrid**, которые затем добавляются в размещаемый повторно [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Справочная информация о коде, который должен содержаться в файле MainWindow.xaml.cs после выполнения трех задач в серии разделов [Повторное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md), приведена в конце данного раздела.  
  
### Создание области элементов и ее добавление к сетке.  
  
1.  Откройте проект HostingApplication, полученный после выполнения процедуры, описанной в [Задание 2. Размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md).  
  
2.  В области **Обозревателя решений** щелкните правой кнопкой мыши файл MainWindow.xaml и выберите пункт **Просмотр кода**.  
  
3.  Добавьте метод `GetToolboxControl` к классу `MainWindow`, создающему <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, добавьте новую категорию **Области элементов** к **Области элементов**, и присвойте этой категории типы действий <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence>.  
  
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
  
4.  Добавьте закрытый метод `AddToolbox` к классу `MainWindow`, размещающему **Область элементов** в левом столбце сетки.  
  
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
  
6.  Нажмите клавишу F5, чтобы построить и выполнить решение.Должна отобразиться область инструментов **Toolbox**, содержащая действия <xref:System.Activities.Statements.Assign> и <xref:System.Activities.Statements.Sequence>.  
  
### Создание области PropertyGrid  
  
1.  В области **Обозревателя решений** щелкните правой кнопкой мыши файл MainWindow.xaml и выберите пункт **Просмотр кода**.  
  
2.  Добавьте метод `AddPropertyInspector` к классу `MainWindow`, чтобы разместить область **PropertyGrid** в самом правом столбце сетки.  
  
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
  
4.  Нажмите клавишу F5 для построения и выполнения решения.Должны отображаться область **Toolbox**, поле визуальной разработки рабочего процесса и области **PropertyGrid**, а при перетаскивании действия <xref:System.Activities.Statements.Assign> или действия <xref:System.Activities.Statements.Sequence> на поле визуальной разработки сетка свойств должна обновиться \(в зависимости от выделенного действия\).  
  
## Пример  
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
  
## См. также  
 [Повторное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Задание 1. Создание нового приложения Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Задание 2. Размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)