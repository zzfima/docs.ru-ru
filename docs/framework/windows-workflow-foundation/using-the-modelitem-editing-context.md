---
title: Использование контекста редактирования ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a47cb53e50d221c0ae07cf0841688fe4f8ced7d4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988922"
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
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a>Создание службы  
 Чтобы создать службу, которая служит каналом передачи между конструктором и узлом, необходимо создать интерфейс и реализацию. Этот интерфейс используется методом <xref:System.Activities.Presentation.ServiceManager.Publish%2A> для определения элементов службы, и реализация содержит логику для этой службы. В следующем примере кода создаются интерфейс службы и реализация.  
  
```csharp  
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
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Подписка на службу  
 Конструктор получает доступ к службе с помощью метода <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> в методе <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. В следующем фрагменте кода показана подписка на службу.  
  
```csharp  
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
 .NET Framework предоставляет ряд встроенных элементов и служб, доступ к которым осуществляется через контекст редактирования.  
  
 Элементы:  
  
- <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Управляет списком локальных сборок, на которые имеются ссылки, которые будут использоваться в рабочем процессе для элементов управления (например, редактор выражений).  
  
- <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Указывает, находится ли конструктор в состоянии только для чтения.  
  
- <xref:System.Activities.Presentation.View.Selection>: Определяет коллекцию объектов, которые выбраны в данный момент.  
  
- <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
- <xref:System.Activities.Presentation.WorkflowFileItem>: Предоставляет сведения о файле, на котором основан текущий сеанс редактирования.  
  
 Службы:  
  
- <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Позволяет добавлять свойства в текущий экземпляр с помощью <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
- <xref:System.Activities.Presentation.View.DesignerView>: Разрешает доступ к свойствам холста конструктора.  
  
- <xref:System.Activities.Presentation.IActivityToolboxService>: Позволяет обновлять содержимое панели элементов.  
  
- <xref:System.Activities.Presentation.Hosting.ICommandService>: Используется для интеграции команд конструктора (например, контекстного меню) с пользовательскими реализациями служб.  
  
- <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Предоставляет функциональные возможности отладчика конструктора.  
  
- <xref:System.Activities.Presentation.View.IExpressionEditorService>: Предоставляет доступ к диалоговому окну редактора выражений.  
  
- <xref:System.Activities.Presentation.IIntegratedHelpService>: Предоставляет конструктор со встроенными функциями справки.  
  
- <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Предоставляет доступ к ошибкам проверки <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>с помощью.  
  
- <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Предоставляет внутреннюю службу для хранения и извлечения данных. Эта служба используется на внутреннем уровне .NET Framework и не предназначена для внешнего использования.  
  
- <xref:System.Activities.Presentation.IXamlLoadErrorService>: Предоставляет доступ к коллекции ошибок загрузки XAML с помощью <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
- <xref:System.Activities.Presentation.Services.ModelService>: Используется конструктором для взаимодействия с моделью редактируемого рабочего процесса.  
  
- <xref:System.Activities.Presentation.Model.ModelTreeManager>: Предоставляет доступ к корню дерева элементов модели с помощью <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
- <xref:System.Activities.Presentation.UndoEngine>: Предоставляет функции отмены и повтора.  
  
- <xref:System.Activities.Presentation.Services.ViewService>: Сопоставляет визуальные элементы с базовыми элементами модели.  
  
- <xref:System.Activities.Presentation.View.ViewStateService>: Сохраняет состояния представления для элементов модели.  
  
- <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Используется для настройки поведения пользовательского интерфейса виртуального контейнера.  
  
- <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Используется для регистрации и отмены регистрации делегатов для уведомлений о событиях. Кроме того, позволяет задавать владельца окна.
