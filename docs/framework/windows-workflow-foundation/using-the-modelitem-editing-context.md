---
title: Использование контекста редактирования ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669502"
---
# <a name="using-the-modelitem-editing-context"></a>Использование контекста редактирования ModelItem
Контекст редактирования <xref:System.Activities.Presentation.Model.ModelItem> является объектом, используемым ведущим приложением для взаимодействия с конструктором. <xref:System.Activities.Presentation.EditingContext> предоставляет два метода, <xref:System.Activities.Presentation.EditingContext.Items%2A> и <xref:System.Activities.Presentation.EditingContext.Services%2A>, которые могут использоваться  
  
## <a name="the-items-collection"></a>Коллекция элементов  
 Коллекция <xref:System.Activities.Presentation.EditingContext.Items%2A> служит для доступа к данным, совместно используемым ведущим приложением и конструктором, либо к данным, доступным для всех конструкторов. Эта коллекция имеет следующие возможности, доступ к которым осуществляется через класс <xref:System.Activities.Presentation.ContextItemManager>:  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a>Коллекция служб  
 Коллекция <xref:System.Activities.Presentation.EditingContext.Services%2A> предназначена для доступа к службам, используемым конструктором для взаимодействия с узлом, либо к службам, используемым всеми конструкторами. Эта коллекция содержит следующие методы, на которые нужно обратить внимание:  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a>Назначение конструктора действию  
 Чтобы указать, какой конструктор используется действием, служит атрибут Designer.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a>Создание службы  
 Чтобы создать службу, которая служит каналом передачи между конструктором и узлом, необходимо создать интерфейс и реализацию. Этот интерфейс используется методом <xref:System.Activities.Presentation.ServiceManager.Publish%2A> для определения элементов службы, и реализация содержит логику для этой службы. В следующем примере кода создаются интерфейс службы и реализация.  
  
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
  
## <a name="publishing-a-service"></a>Публикация службы  
 Чтобы конструктор мог использовать службу, ее сначала необходимо опубликовать на узле с помощью метода <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Подписка на службу  
 Конструктор получает доступ к службе с помощью метода <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> в методе <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. В следующем фрагменте кода показана подписка на службу.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Совместное использование данных с помощью коллекции элементов  
 Работа с коллекцией элементов похожа на работу с коллекцией служб, за исключением того, что вместо Publish вызывается <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>. Эта коллекция больше подходит для обмена простыми данными между конструкторами и узлом, чем для выполнения сложных функций.  
  
## <a name="editingcontext-host-items-and-services"></a>Ведущие элементы узла EditingContext и службы  
 .NET Framework предоставляет ряд встроенных элементов и служб, через контекст редактирования.  
  
 Элементы:  
  
- <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Управляет списком локальных сборок, которые будут использоваться в рабочем процессе для элементов управления (например, в редакторе выражений).  
  
- <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Указывает, находится ли конструктор в состоянии только для чтения.  
  
- <xref:System.Activities.Presentation.View.Selection>: Определяет коллекцию объектов, выбранных в настоящее время.  
  
- <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
- <xref:System.Activities.Presentation.WorkflowFileItem>: Сведения о файле, который зависит от текущего сеанса.  
  
 Службы:  
  
- <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Позволяет добавлять в текущий экземпляр свойства с помощью <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
- <xref:System.Activities.Presentation.View.DesignerView>: Разрешает доступ к свойствам полотна конструктора.  
  
- <xref:System.Activities.Presentation.IActivityToolboxService>: Допускает содержание элементов обновляться.  
  
- <xref:System.Activities.Presentation.Hosting.ICommandService>: Используется для интеграции команд конструктора (например, контекстное меню) с реализациями пользовательские службы.  
  
- <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Предоставляет функциональные возможности отладчика конструктора.  
  
- <xref:System.Activities.Presentation.View.IExpressionEditorService>: Предоставляет доступ к диалоговому окну редактора выражений.  
  
- <xref:System.Activities.Presentation.IIntegratedHelpService>: Реализует в конструкторе функциональность встроенной справки.  
  
- <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Предоставляет доступ к ошибкам проверки через <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
- <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: -Реализует внутреннюю службу для хранения и извлечения данных. Эта служба является внутренним классом .NET Framework и не предназначен для внешнего использования.  
  
- <xref:System.Activities.Presentation.IXamlLoadErrorService>: Предоставляет доступ к XAML нагрузки ошибка коллекции с помощью <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
- <xref:System.Activities.Presentation.Services.ModelService>: Используется конструктором для взаимодействия с моделью редактируемого рабочего процесса.  
  
- <xref:System.Activities.Presentation.Model.ModelTreeManager>: Предоставляет доступ к корню дерева элементов модели, используя <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
- <xref:System.Activities.Presentation.UndoEngine>: Предоставляет отмены и возврата.  
  
- <xref:System.Activities.Presentation.Services.ViewService>: Сопоставляет визуальные элементы с элементами базовой модели.  
  
- <xref:System.Activities.Presentation.View.ViewStateService>: Сохраняет состояния представления для элементов модели.  
  
- <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Используется для настройки поведения пользовательского интерфейса виртуального контейнера.  
  
- <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Используется для регистрации и отмены регистрации делегатов для уведомлений о событиях. Кроме того, позволяет задавать владельца окна.
