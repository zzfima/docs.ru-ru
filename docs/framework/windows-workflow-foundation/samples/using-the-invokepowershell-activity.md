---
title: "Использование действия InvokePowerShell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ea3106f87dae64204ea0c02a1388ed8893c858b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-invokepowershell-activity"></a>Использование действия InvokePowerShell
Образец InvokePowerShell демонстрирует, как вызывать команды Windows PowerShell с помощью действия `InvokePowerShell`.  
  
## <a name="demonstrates"></a>Демонстрации  
  
-   Простой новый метод использования команд Windows PowerShell.  
  
-   Получите значения из канала выходных данных Windows PowerShell и сохраните их в переменных рабочего процесса.  
  
-   Передайте данные в Windows PowerShell в виде канала входных данных для исполняемой команды.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a>Обсуждение  
 Этот образец содержит следующие три проекта.  
  
|Имя проекта|Описание|Основные файлы|  
|------------------|-----------------|----------------|  
|CodedClient|Образец клиентского приложения, использующий действие PowerShell.|-   **Program.cs**: программным образом создает рабочий процесс на основе последовательности, вызывающей действие InvokePowerShell.|  
|DesignerClient|Набор пользовательских действий, содержащих пользовательское действие `InvokePowerShell`, прочие пользовательские действия и рабочий процесс, использующий их.|<ul><li>Действия:<br /><br /> <ul><li>**PrintCollection.cs**: вспомогательное действие, выводящее все элементы в коллекции на консоль.</li><li>**ReadLine.cs**: вспомогательное действие для чтения данные с консоли.</li></ul></li><li>Файловая система:<br /><br /> <ul><li>**Copy.XAML**: действие, копирующее файл.</li><li>**CreateFile.xaml**: действие, создающее файл.</li><li>**DeleteFile.xaml**: действие, которое удаляет файл.</li><li>**MakeDir.xaml**: действие, которое создает каталог.</li><li>**MOVE.XAML**: действие, перемещающее файл.</li><li>**ReadFile.xaml**: действие, которое считывает файл и возвращает его содержимое.</li><li>**TestPath.xaml**: действие, проверяющее наличие пути.</li></ul></li><li>Процесс:<br /><br /> <ul><li>**GetProcess.xaml**: действие, возвращающее перечень запущенных процессов.</li><li>**StopProcess.xaml**: действие, останавливающее конкретный процесс.</li></ul></li><li>**Program.cs**: вызывает рабочий процесс Sequence1.</li><li>**Sequence1.XAML**: рабочий процесс на основе последовательности.</li></ul>|  
|PowerShell|Действие `InvokePowerShell` и связанные с ним конструкторы.|Файлы действия<br /><br /> -   **ExecutePowerShell.cs**: основной логики выполнения действия.<br />-   **InvokePowerShell.cs**: оболочка главной логики исполнения, который содержит стандартную (возвращающую значение) версию и нестандартную (не возвращающую значение) версию. Это открытый интерфейс действия.<br />-   **NoPersistZone.cs**: это действие препятствующее сохранению дочерних действий. Данный класс используется в реализации действия `InvokePowerShell` для предотвращения сохранения действия в ходе исполнения.<br /><br /> Файлы конструктора:<br /><br /> 1.  **ArgumentDictionaryEditor.cs**: диалог Windows, который позволяет пользователю изменять аргументы `InvokePowerShell` действия.<br />2.  **GenericInvokePowerShellDesigner.xaml** и **GenericInvokePowerShellDesigner.xaml.cs**: Определяет внешний вид универсального `InvokePowerShell` действия в [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].<br />3.  **InvokePowerShellDesigner.xaml** и **InvokePowerShellDesigner.cs**: Определяет внешний вид неуниверсальные `InvokePowerShell` действия в [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].|  
  
 Клиентские проекты обсуждаются в первую очередь, поскольку проще понять внутреннее функционирование действия PowerShell, изучив его практическое применение.  
  
## <a name="using-this-sample"></a>Использование этого образца  
 В следующих разделах описано, как использовать три проекта в образце.  
  
### <a name="using-the-coded-client-project"></a>Использование закодированного клиентского проекта.  
 Образец клиента программным образом создает действие `InvokePowerShell`. При первом вызове запускается блокнот.  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 При втором вызове возвращается перечень процессов, запущенных на локальном компьютере.  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 `Output` - это переменная, используемая для хранения выходных данных команды.  
  
 При следующем вызове показывается, как запускать стадию завершающей обработки для каждого отдельного выхода вызова PowerShell. `InitializationAction` задается как функция, выводящая строчное представление каждого процесса. Коллекция этих строк возвращается в переменную `Output` действием `InvokePowerShell<string>`.  
  
 При последующем вызове `InvokePowerShell` демонстрируется передача данных действию и вывод конечных данных и ошибок.  
  
### <a name="using-the-designer-client-project"></a>Использование конструкторского клиентского проекта.  
 Проект DesignerClient состоит из набора пользовательских действий, большинство из которых содержат действие `InvokePowerShell`. Большинство действий вызывают нестандартную версию действия `InvokePowerShell` и не ожидают возвращаемого значения. Прочие действия применяют стандартную версию действия `InvokePowerShell` и аргумент `InitializationAction` для последующей обработки результатов.  
  
## <a name="using-the-powershell-project"></a>Использование проекта PowerShell  
 Главное действие действия совершается в классе `ExecutePowerShell`. Поскольку исполнение команд PowerShell не должно блокировать поток главного рабочего процесса, действие создается как асинхронное путем наследования от класса <xref:System.Activities.AsyncCodeActivity>.  
  
 Метод <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> вызывается средой выполнения рабочего процесса, чтобы начать исполнение действия. Для начала вызываются методы API-интерфейса PowerShell, чтобы создать конвейер PowerShell.  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 Затем создается команда PowerShell, которая заполняется параметрами и переменными.  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 Входящие исходные данные в этот момент также отправляются в конвейер. Наконец, конвейер получает оболочку из объекта `PipelineInvokerAsyncResult` и возвращается. Объект `PipelineInvokerAsyncResult` регистрирует прослушиватель и вызывает конвейер.  
  
```  
pipeline.InvokeAsync();  
```  
  
 После успешного выполнения конечные данные и ошибки сохраняются в том же объекте `PipelineInvokerAsyncResult`, а контроль возвращается среде выполнения рабочего процесса путем вызова метода обратного вызова, изначально переданного через параметр <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.  
  
 В конце исполнения метода среда выполнения рабочего процесса вызывает метод <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> действия.  
  
 Класс `InvokePowerShell` создает оболочку для класса `ExecutePowerShellCommand` и две версии действия: стандартную и нестандартную. Нестандартная версия возвращает конечные данные работы PowerShell непосредственно, а стандартная преобразует индивидуальные результаты в стандартный тип.  
  
 Стандартная версия действия реализуется как последовательный рабочий процесс, вызывающий команду `ExecutePowerShellCommand` и проводящий конечную обработку ее результатов. Для каждого элемента из коллекции результатов на стадии конечной обработки вызывается действие `InitializationAction`. если оно задано. В противном случае осуществляется простое приведение.  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 Для каждого из двух действий `InvokePowerShell` (стандартного и нестандартного) создается конструктор. InvokePowerShellDesigner.xaml и связанный с ним CS-файл определяют внешний вид в средстве [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] нестандартного действия `InvokePowerShell`. Внутри InvokePowerShellDesigner.xaml <xref:System.Windows.Controls.DockPanel> представляет графический интерфейс.  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 Стоит заметить, что свойство `Text` текстового поля является двусторонней привязкой, гарантирующей, что значение свойства `CommandText` действия будет эквивалентно значению, вводимому в конструктор.  
  
 GenericInvokePowerShellDesigner.xaml и связанный с ним CS-файл определяют графический интерфейс `InvokePowerShell` нестандартного действия. Конструктор немного сложнее, поскольку позволяет пользователям задавать `InitializationAction`. Ключевой элемент применения <xref:System.Activities.Presentation.WorkflowItemPresenter> - это возможность перетаскивать дочерние действия в область конструктора `InvokePowerShell`.  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 Настройка конструктора не завершается настройкой XAML-файлов, определяющих внешний вид действия на холсте конструктора. Диалоговые окна, используемые для отображения параметров действия, тоже можно настроить. Эти параметры и переменные PowerShell влияют на поведение команд PowerShell. Это действие предоставляет их в виде <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` типов. ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml и PropertyEditorResources.cs определяют диалоговое окно, позволяющее изменять эти типы.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
 Чтобы запустить этот образец, нужно установить Windows PowerShell. Windows PowerShell можно установить из этого расположения: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).  
  
#### <a name="to-run-the-coded-client"></a>Запуск закодированного клиента  
  
1.  Откройте файл PowerShell.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Щелкните решение правой кнопкой мыши и постройте его.  
  
3.  Щелкните правой кнопкой мыши **CodedClient** проект и выберите **Назначить запускаемым проектом**.  
  
4.  Нажмите CTRL+F5, чтобы запустить приложение.  
  
#### <a name="to-run-the-designer-client"></a>Запуск конструкторского клиента  
  
1.  Откройте файл PowerShell.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Щелкните решение правой кнопкой мыши и постройте его.  
  
3.  Щелкните правой кнопкой мыши **DesignerClient** проект и выберите **Назначить запускаемым проектом**.  
  
4.  Нажмите CTRL+F5, чтобы запустить приложение.  
  
## <a name="known-issues"></a>Известные проблемы  
  
1.  Если при обращении к сборке с действиями `InvokePowerShell` или проекту от другого проекта возникает ошибка, возможно, нужно вручную добавить элемент `<SpecificVersion>True</SpecificVersion>` к CSPROJ-файлу нового проекта под строчкой, в которой происходит обращение к `InvokePowerShell`.  
  
2.  Если не установлена оболочка Windows PowerShell, следующее сообщение об ошибке отображается в Visual Studio, сразу после добавления `InvokePowerShell` действия в рабочий процесс:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`  
  
3.  В среде Windows PowerShell 2.0 не удался вызов `$input.MoveNext()` программным образом, а в скриптах, использующих `$input.MoveNext()`, формируются непреднамеренные ошибки и результаты. Чтобы решить эту проблему, попробуйте использовать операцию PowerShell `foreach`, вместо того, чтобы вызывать `MoveNext()` при проходе по массиву.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`