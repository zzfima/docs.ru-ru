---
title: "Использование контекста редактирования ModelItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Использование контекста редактирования ModelItem
Контекст редактирования <xref:System.Activities.Presentation.Model.ModelItem> является объектом, используемым ведущим приложением для взаимодействия с конструктором.<xref:System.Activities.Presentation.EditingContext> предоставляет два метода, <xref:System.Activities.Presentation.EditingContext.Items%2A> и <xref:System.Activities.Presentation.EditingContext.Services%2A>, которые могут использоваться  
  
## Коллекция элементов  
 Коллекция <xref:System.Activities.Presentation.EditingContext.Items%2A> служит для доступа к данным, совместно используемым основным приложением и конструктором, либо к данным, доступным для всех конструкторов.Эта коллекция имеет следующие возможности, доступ к которым осуществляется через класс <xref:System.Activities.Presentation.ContextItemManager>:  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## Коллекция служб  
 Коллекция <xref:System.Activities.Presentation.EditingContext.Services%2A> предназначена для доступа к службам, используемым конструктором для взаимодействия с узлом, либо к службам, используемым всеми конструкторами.Эта коллекция содержит следующие методы, на которые нужно обратить внимание:  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## Назначение конструктора действию  
 Чтобы указать, какой конструктор используется действием, служит атрибут Designer.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
  
```  
  
## Создание службы  
 Чтобы создать службу, которая служит каналом передачи между конструктором и узлом, необходимо создать интерфейс и реализацию.Этот интерфейс используется методом <xref:System.Activities.Presentation.ServiceManager.Publish%2A> для определения элементов службы, и реализация содержит логику для этой службы.В следующем примере кода создаются интерфейс службы и реализация.  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
  
```  
  
## Публикация службы  
 Чтобы конструктор мог использовать службу, ее сначала необходимо опубликовать на узле с помощью метода <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## Подписка на службу  
 Конструктор получает доступ к службе с помощью метода <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> в методе <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.В следующем фрагменте кода показана подписка на службу.  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
  
```  
  
## Совместное использование данных с помощью коллекции элементов  
 Работа с коллекцией элементов похожа на работу с коллекцией служб, за исключением того, что вместо Publish вызывается <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>.Эта коллекция больше подходит для обмена простыми данными между конструкторами и узлом, чем для выполнения сложных функций.  
  
## Ведущие элементы узла EditingContext и службы  
 Среда .Net Framework предусматривает несколько встроенных элементов и служб, доступ к которым осуществляется через контекст редактирования.  
  
 Элементы:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem> — управляет списком локальных сборок, на которые указывают ссылки и которые будут использоваться в рабочем процессе для элементов управления \(например, в редакторе выражений\).  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState> — указывает, находится ли конструктор в режиме только для чтения.  
  
-   <xref:System.Activities.Presentation.View.Selection> — определяет коллекцию выбранных в настоящий момент объектов.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem> — предоставляет сведения о файле, на основе которого выполняется текущий сеанс редактирования.  
  
 Службы:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService> — позволяет добавлять свойства в текущий экземпляр с помощью <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
-   <xref:System.Activities.Presentation.View.DesignerView> — разрешает доступ к свойствам полотна конструктора.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService> — позволяет обновлять содержимое области элементов.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService> — предназначен для интеграции команд конструктора \(например, пунктов контекстного меню\) с пользовательскими реализациями службы.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView> — обеспечивает функциональность отладчика конструктора.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService> — обеспечивает доступ к диалоговому окну редактора выражений.  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService> — реализует в конструкторе функциональность встроенной справки.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService> — обеспечивает доступ к ошибкам проверки через <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService> — реализует внутреннюю службу для хранения и извлечения данных.Эта служба используется внутри среды .Net Framework и не предназначена для внешнего использования.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService> — предоставляет доступ к коллекции ошибок загрузки XAML через <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
-   <xref:System.Activities.Presentation.Services.ModelService> — используется конструктором для взаимодействия с редактируемой моделью рабочего процесса.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager> — обеспечивает доступ к корневому элементу дерева элементов модели через <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
-   <xref:System.Activities.Presentation.UndoEngine> — реализует функциональность отмены и повтора операций.  
  
-   <xref:System.Activities.Presentation.Services.ViewService> — сопоставляет визуальные элементы с элементами базовой модели.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService> — сохраняет состояния представления для элементов модели.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService> — используется для настройки поведения пользовательского интерфейса виртуального контейнера.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService> — служит для регистрации и отмены регистрации делегатов для уведомления о событиях.Кроме того, позволяет задавать владельца окна.