---
title: "Использование действия &#171;Interop&#187; в рабочем процессе платформы .NET Framework 4 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Использование действия &#171;Interop&#187; в рабочем процессе платформы .NET Framework 4
Действия, созданные с помощью [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] или [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] может использоваться в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса с помощью <xref:System.Activities.Statements.Interop> действия. В этом разделе содержатся сведения об использовании <xref:System.Activities.Statements.Interop> действия.  
  
> [!NOTE]
>   <xref:System.Activities.Statements.Interop> действия не отображается в области элементов конструктора рабочих процессов, если проект рабочего процесса содержит его **Требуемая версия .NET Framework** задано значение **.Net Framework 4** или более поздней версии.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>Использование действия Interop в рабочих процессах платформы .NET Framework 4.5  
 В данном разделе создается библиотека действий [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], содержащая действие `DiscountCalculator`.  `DiscountCalculator` Вычисляет скидку, основанную на приобретений и состоит из <xref:System.Workflow.Activities.SequenceActivity> содержащий <xref:System.Workflow.Activities.PolicyActivity>.  
  
> [!NOTE]
>   [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] Действие, созданный в данном разделе использует <xref:System.Workflow.Activities.PolicyActivity> для реализации логики действия. Он не требуется для использования пользовательского [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] действия или <xref:System.Activities.Statements.Interop> действие, чтобы использовать правила в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса. Пример использования правил в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса без использования <xref:System.Activities.Statements.Interop> действие, в разделе [действие политики в .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) образца.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>Создание проекта библиотеки действий платформы .NET Framework 3.5  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и выберите **New** и затем **проекта...** из **файла** меню.  
  
2.  Разверните **другие типы проектов** узел в **Установленные шаблоны** панели и выберите **решения Visual Studio**.  
  
3.  Выберите **пустое решение** из **решения Visual Studio** списка. Тип `PolicyInteropDemo` в **имя** и нажмите кнопку **ОК**.  
  
4.  Щелкните правой кнопкой мыши **PolicyInteropDemo** в **обозревателе решений** и выберите **Добавить** и затем **Создать проект...**.  
  
    > [!TIP]
    >  Если **обозревателе решений** окно не отображается, выберите пункт **обозревателе решений** из **представления** меню.  
  
5.  В **Установленные шаблоны** выберите **Visual C#** и затем **рабочего процесса**. Выберите **.NET Framework 3.5** раскрывающемся списке версий .NET Framework, а затем выберите **Библиотека действий рабочих процессов** из **шаблонов** списка.  
  
6.  Тип `PolicyActivityLibrary` в **имя** и нажмите кнопку **ОК**.  
  
7.  Щелкните правой кнопкой мыши **Activity1.cs** в **обозревателе решений** и выберите **Удаление**. Нажмите кнопку **ОК** для подтверждения.  
  
#### <a name="to-create-the-discountcalculator-activity"></a>Создание действия DiscountCalculator  
  
1.  Щелкните правой кнопкой мыши **PolicyActivityLibrary** в **обозревателе решений** и выберите **Добавить** и затем **действие...**.  
  
2.  Выберите **действие (с разделением кода)** из **элементы Visual C#** списка. Тип `DiscountCalculator` в **имя** и нажмите кнопку **ОК**.  
  
3.  Щелкните правой кнопкой мыши **DiscountCalculator.xoml** в **обозревателе решений** и выберите **Просмотр кода**.  
  
4.  Добавьте в класс `DiscountCalculator` приведенные ниже три свойства.  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  Щелкните правой кнопкой мыши **DiscountCalculator.xoml** в **обозревателе решений** и выберите **Конструктор представлений**.  
  
6.  Перетащите **политика** действие из **Windows Workflow v3.0** раздел **элементов** и поместите его **DiscountCalculator** действия.  
  
    > [!TIP]
    >  Если **элементов** окно не отображается, выберите пункт **элементов** из **представления** меню.  
  
#### <a name="to-configure-the-rules"></a>Настройка правил  
  
1.  Щелкните только что добавленном **политика** действие, выберите его, если он еще не выбран.  
  
2.  Щелкните **RuleSetReference** Свойства **Свойства** окно, чтобы выбрать его и нажмите кнопку с многоточием справа от свойства.  
  
    > [!TIP]
    >  Если **Свойства** окно не отображается, выберите **окно свойств** из **представления** меню.  
  
3.  Выберите **нажмите кнопку Создать...**.  
  
4.  Щелкните **Добавить правило**.  
  
5.  Введите следующее выражение в **условие** поле.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  Введите следующее выражение в **действия Then** поле.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  Щелкните **Добавить правило**.  
  
8.  Введите следующее выражение в **условие** поле.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. Введите следующее выражение в **действия Then** поле.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. Щелкните **Добавить правило**.  
  
11. Введите следующее выражение в **условие** поле.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. Введите следующее выражение в **действия Then** поле.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. Введите следующее выражение в **действия Else** поле.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. Щелкните **ОК** Закрыть **Редактор набора правил** диалоговое окно.  
  
15. Убедитесь, что только что созданный <xref:System.Workflow.Activities.Rules.RuleSet> выбран в **имя** и выберите **ОК**.  
  
16. Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
 Правила, добавленные в действие `DiscountCalculator` в ходе выполнения этой процедуры, показаны в следующем примере кода.  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 Когда <xref:System.Workflow.Activities.PolicyActivity> выполняет эти три правила оценить и модифицировать `Subtotal`, `DiscountPercent`, и `Total` значения свойств `DiscountCalculator` Действие вычисления требуемой скидки.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Использование действия DiscountCalculator совместно с действием Interop  
 Для использования `DiscountCalculator` действия внутри [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] рабочего процесса, <xref:System.Activities.Statements.Interop> используется действие. В этом разделе создаются два рабочих процесса, один с помощью кода и один в конструкторе рабочих процессов, которые демонстрируют использование <xref:System.Activities.Statements.Interop> действия `DiscountCalculator` действия. Для обоих рабочих процессов используется одно ведущее приложение.  
  
#### <a name="to-create-the-host-application"></a>Создание ведущего приложения  
  
1.  Щелкните правой кнопкой мыши **PolicyInteropDemo** в **обозревателе решений** и выберите **Добавить**, а затем **Создать проект...**.  
  
2.  Убедитесь, что **.NET Framework 4.5** выбран в раскрывающемся списке версий .NET Framework и выберите  **Консольное приложение рабочего процесса** из **элементы Visual C#** списка.  
  
3.  Тип `PolicyInteropHost` в **имя** и нажмите кнопку **ОК**.  
  
4.  Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Свойства**.  
  
5.  В **Требуемая версия .NET framework** раскрывающийся список, измените выделенный фрагмент из **клиентский профиль .NET Framework 4** для **.NET Framework 4.5**. Щелкните **Да** для подтверждения.  
  
6.  Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Добавить ссылку**.  
  
7.  Выберите **PolicyActivityLibrary** из **проекты** и нажмите кнопку **ОК**.  
  
8.  Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Добавить ссылку**.  
  
9. Выберите **System.Workflow.Activities**, **System.Workflow.ComponentModel**, а затем **System.Workflow.Runtime** из **.NET** и нажмите кнопку **ОК**.  
  
10. Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Назначить запускаемым проектом**.  
  
11. Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
### <a name="using-the-interop-activity-in-code"></a>Использование действия Interop в коде  
 В этом примере создается определение рабочего процесса с помощью кода, который содержит <xref:System.Activities.Statements.Interop> действия и `DiscountCalculator` действия. Этот рабочий процесс вызывается с помощью <xref:System.Activities.WorkflowInvoker> и результаты оценки правила записываются в консоль с помощью <xref:System.Activities.Statements.WriteLine> действия.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>Использование действия Interop в коде  
  
1.  Щелкните правой кнопкой мыши **Program.cs** в **обозревателе решений** и выберите **Просмотр кода**.  
  
2.  Добавьте следующую инструкцию`using` в начало файла.  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  Удалите содержимое метода `Main` и замените его следующим кодом.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  Создайте новый метод в классе `Program` с именем `CalculateDiscountUsingCodeWorkflow`, который содержит следующий код.  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >   `Subtotal`, `DiscountPercent`, И `Total` Свойства `DiscountCalculator` действия отображаются как аргументы <xref:System.Activities.Statements.Interop> действия и привязанные к локальным переменным рабочего процесса в <xref:System.Activities.Statements.Interop> действия <xref:System.Activities.Statements.Interop.ActivityProperties%2A> коллекции. `Subtotal` добавляется как <xref:System.Activities.ArgumentDirection> аргумент из-за `Subtotal` данные перемещаются в <xref:System.Activities.Statements.Interop> действия, и `DiscountPercent` и `Total` добавляются как <xref:System.Activities.ArgumentDirection> аргументы, так как их потоки данных из <xref:System.Activities.Statements.Interop> действия. Обратите внимание, что два <xref:System.Activities.ArgumentDirection> Аргументы добавляются с именами `DiscountPercentOut` и `TotalOut` для указания, что они представляют <xref:System.Activities.ArgumentDirection> аргументы.  `DiscountCalculator` Тип определяется как <xref:System.Activities.Statements.Interop> действия <xref:System.Activities.Statements.Interop.ActivityType%2A>.  
  
5.  Нажмите клавиши CTRL+F5 для сборки и запуска приложения. Подставляя различные значения в качестве значения `Subtotal`, можно проверить различные уровни скидок, реализуемые действием `DiscountCalculator`.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Использование действия Interop в конструкторе рабочих процессов  
 В данном примере рабочий процесс создается с использованием конструктора рабочих процессов. Этот рабочий процесс выполняет аналогичен предыдущему примеру, за исключением того, вместо использования <xref:System.Activities.Statements.WriteLine> мероприятие для отображения скидки ведущее приложение получает и отображает сведения о скидке при завершении рабочего процесса. Также локальные переменные рабочего процесса не используются для хранения данных. Вместо этого аргументы создаются в конструкторе рабочих процессов, а значения передаются из ведущего приложения при вызове рабочего процесса.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>Размещение PolicyActivity с использованием рабочего процесса, созданного в конструкторе рабочих процессов  
  
1.  Щелкните правой кнопкой мыши **Workflow1.xaml** в **обозревателе решений** и выберите **Удаление**. Нажмите кнопку **ОК** для подтверждения.  
  
2.  Щелкните правой кнопкой мыши **PolicyInteropHost** в **обозревателе решений** и выберите **Добавить**, **новый элемент...**.  
  
3.  Разверните **элементы Visual C#** и выберите команду **рабочего процесса**. Выберите **действия** из **элементы Visual C#** списка.  
  
4.  Тип `DiscountWorkflow` в **имя** и нажмите кнопку **Добавить**.  
  
5.  Щелкните **аргументы** кнопки в нижнем левом углу конструктора рабочих процессов для отображения **аргументы** области.  
  
6.  Щелкните **Создать аргумент**.  
  
7.  Тип `Subtotal` в **имя** выберите **в** из **направление** раскрывающийся список, выберите **двойные** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.  
  
    > [!NOTE]
    >  Если **двойные** не находится в **тип аргумента** раскрывающемся списке выберите **Обзор типов …**, тип `System.Double` в **имя типа** и нажмите кнопку **ОК**.  
  
8.  Щелкните **Создать аргумент**.  
  
9. Тип `DiscountPercent` в **имя** выберите **Out** из **направление** раскрывающийся список, выберите **двойные** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.  
  
10. Щелкните **Создать аргумент**.  
  
11. Тип `Total` в **имя** выберите **Out** из **направление** раскрывающийся список, выберите **двойные** из **тип аргумента** раскрывающегося списка и нажмите клавишу ВВОД, чтобы сохранить аргумент.  
  
12. Щелкните **аргументы** кнопки в нижнем левом углу конструктора рабочих процессов, чтобы закрыть **аргументы** области.  
  
13. Перетащите **последовательность** действия из **поток управления** раздел **элементов** и поместите его на поверхность конструктора рабочих процессов.  
  
14. Перетащите **взаимодействия** действия из **миграции** раздел **элементов** и поместите его **последовательность** действия.  
  
15. Щелкните **взаимодействия** действие на **щелкните для просмотра...** Метка, введите **DiscountCalculator** в **имя типа** и нажмите кнопку **ОК**.  
  
    > [!NOTE]
    >  При <xref:System.Activities.Statements.Interop> добавляется действие рабочего процесса и `DiscountCalculator` тип определяется как его <xref:System.Activities.Statements.Interop.ActivityType%2A>,  <xref:System.Activities.Statements.Interop> действие предоставляет три <xref:System.Activities.ArgumentDirection> аргументы и три <xref:System.Activities.ArgumentDirection> аргументы, представляющие три открытых свойства `DiscountCalculator` действия.  <xref:System.Activities.ArgumentDirection> аргументы имеют имя, совпадающее с именем три открытых свойства, а также три <xref:System.Activities.ArgumentDirection> аргументы имеют те же имена с **ожидания** добавляется к имени свойства. В следующих шагах аргументы рабочего процесса, созданный на предыдущих шагах, привязываются к <xref:System.Activities.Statements.Interop> аргументов действия.  
  
16. Тип `DiscountPercent` в **Введите выражение VB** поле справа от **DiscountPercentOut** свойство и нажмите клавишу TAB.  
  
17. Тип `Subtotal` в **Введите выражение VB** поле справа от **Subtotal** свойство и нажмите клавишу TAB.  
  
18. Тип `Total` в **Введите выражение VB** поле справа от **TotalOut** свойство и нажмите клавишу TAB.  
  
19. Щелкните правой кнопкой мыши **Program.cs** в **обозревателе решений** и выберите **Просмотр кода**.  
  
20. Добавьте следующую инструкцию`using` в начало файла.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. Закомментируйте вызов метода `CalculateDiscountInCode` в методе `Main` и добавьте следующий код.  
  
    > [!NOTE]
    >  Если предыдущая процедура не была выполнена и код `Main` по умолчанию все еще присутствует, замените содержимое метода `Main` следующим кодом.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. Создайте новый метод в классе `Program` с именем `CalculateDiscountUsingDesignerWorkflow`, который содержит следующий код.  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. Нажмите клавиши CTRL+F5 для сборки и запуска приложения. Чтобы задать другую сумму `Subtotal`, измените значение `SubtotalValue` в следующем коде.  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>Общие сведения об особенностях правил  
 Обработчик правил [!INCLUDE[wf1](../../../includes/wf1-md.md)] обеспечивает поддержку обработки правил с учетом приоритетов и поддержкой прямых логических цепочек. Оценка правил может проводиться для одного элемента или для элементов коллекции. Общие сведения о правилах, а также сведения о функциональных возможностях отдельных правил см. в следующей таблице.  
  
|Возможность правил|Документация|  
|-------------------|-------------------|  
|Общие сведения о правилах|[Введение в обработчик правил Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[Использование наборов правил в рабочих процессах](http://go.microsoft.com/fwlink/?LinkId=178516) и <xref:System.Workflow.Activities.Rules.RuleSet>|  
|Оценка правил|[Оценка правил в наборах правил](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|Цепочки правил|[Управление прямой цепочкой](http://go.microsoft.com/fwlink/?LinkId=178518) и [правил прямой цепочки](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|Обработка коллекций в правилах|[Обработка коллекций в правилах](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|Использование действия PolicyActivity|[Использование действия PolicyActivity](http://go.microsoft.com/fwlink/?LinkId=178521) и <xref:System.Workflow.Activities.PolicyActivity>|  
  
 Рабочие процессы, созданные в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] не использовать все возможности правил, предоставляемых [!INCLUDE[wf1](../../../includes/wf1-md.md)], например декларативных условий действий и условные действия, такие как <xref:System.Workflow.Activities.ConditionedActivityGroup> и <xref:System.Workflow.Activities.ReplicatorActivity>. При необходимости можно воспользоваться этими функциональными возможностями в рабочих процессах, созданных с помощью [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] и [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Руководство по миграции](../../../docs/framework/windows-workflow-foundation//migration-guidance.md).