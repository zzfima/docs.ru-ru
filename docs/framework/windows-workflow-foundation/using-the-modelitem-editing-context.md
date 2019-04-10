---
title: Использование контекста редактирования ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: a2628bbbf2f6684e5d484b05cd5a2ac622f3b664
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296893"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="38b02-102">Использование контекста редактирования ModelItem</span><span class="sxs-lookup"><span data-stu-id="38b02-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="38b02-103">Контекст редактирования <xref:System.Activities.Presentation.Model.ModelItem> является объектом, используемым ведущим приложением для взаимодействия с конструктором.</span><span class="sxs-lookup"><span data-stu-id="38b02-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <xref:System.Activities.Presentation.EditingContext> <span data-ttu-id="38b02-104">предоставляет два метода <xref:System.Activities.Presentation.EditingContext.Items%2A> и <xref:System.Activities.Presentation.EditingContext.Services%2A>, который может использоваться</span><span class="sxs-lookup"><span data-stu-id="38b02-104">exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="38b02-105">Коллекция элементов</span><span class="sxs-lookup"><span data-stu-id="38b02-105">The Items collection</span></span>  
 <span data-ttu-id="38b02-106">Коллекция <xref:System.Activities.Presentation.EditingContext.Items%2A> служит для доступа к данным, совместно используемым ведущим приложением и конструктором, либо к данным, доступным для всех конструкторов.</span><span class="sxs-lookup"><span data-stu-id="38b02-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="38b02-107">Эта коллекция имеет следующие возможности, доступ к которым осуществляется через класс <xref:System.Activities.Presentation.ContextItemManager>:</span><span class="sxs-lookup"><span data-stu-id="38b02-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="38b02-108">Коллекция служб</span><span class="sxs-lookup"><span data-stu-id="38b02-108">The Services collection</span></span>  
 <span data-ttu-id="38b02-109">Коллекция <xref:System.Activities.Presentation.EditingContext.Services%2A> предназначена для доступа к службам, используемым конструктором для взаимодействия с узлом, либо к службам, используемым всеми конструкторами.</span><span class="sxs-lookup"><span data-stu-id="38b02-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="38b02-110">Эта коллекция содержит следующие методы, на которые нужно обратить внимание:</span><span class="sxs-lookup"><span data-stu-id="38b02-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="38b02-111">Назначение конструктора действию</span><span class="sxs-lookup"><span data-stu-id="38b02-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="38b02-112">Чтобы указать, какой конструктор используется действием, служит атрибут Designer.</span><span class="sxs-lookup"><span data-stu-id="38b02-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="38b02-113">Создание службы</span><span class="sxs-lookup"><span data-stu-id="38b02-113">Creating a service</span></span>  
 <span data-ttu-id="38b02-114">Чтобы создать службу, которая служит каналом передачи между конструктором и узлом, необходимо создать интерфейс и реализацию.</span><span class="sxs-lookup"><span data-stu-id="38b02-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="38b02-115">Этот интерфейс используется методом <xref:System.Activities.Presentation.ServiceManager.Publish%2A> для определения элементов службы, и реализация содержит логику для этой службы.</span><span class="sxs-lookup"><span data-stu-id="38b02-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="38b02-116">В следующем примере кода создаются интерфейс службы и реализация.</span><span class="sxs-lookup"><span data-stu-id="38b02-116">In the following code example, a service interface and implementation are created.</span></span>  
  
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
  
## <a name="publishing-a-service"></a><span data-ttu-id="38b02-117">Публикация службы</span><span class="sxs-lookup"><span data-stu-id="38b02-117">Publishing a service</span></span>  
 <span data-ttu-id="38b02-118">Чтобы конструктор мог использовать службу, ее сначала необходимо опубликовать на узле с помощью метода <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="38b02-119">Подписка на службу</span><span class="sxs-lookup"><span data-stu-id="38b02-119">Subscribing to a service</span></span>  
 <span data-ttu-id="38b02-120">Конструктор получает доступ к службе с помощью метода <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> в методе <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="38b02-121">В следующем фрагменте кода показана подписка на службу.</span><span class="sxs-lookup"><span data-stu-id="38b02-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="38b02-122">Совместное использование данных с помощью коллекции элементов</span><span class="sxs-lookup"><span data-stu-id="38b02-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="38b02-123">Работа с коллекцией элементов похожа на работу с коллекцией служб, за исключением того, что вместо Publish вызывается <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="38b02-124">Эта коллекция больше подходит для обмена простыми данными между конструкторами и узлом, чем для выполнения сложных функций.</span><span class="sxs-lookup"><span data-stu-id="38b02-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="38b02-125">Ведущие элементы узла EditingContext и службы</span><span class="sxs-lookup"><span data-stu-id="38b02-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="38b02-126">.NET Framework предоставляет ряд встроенных элементов и служб, через контекст редактирования.</span><span class="sxs-lookup"><span data-stu-id="38b02-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="38b02-127">Элементы:</span><span class="sxs-lookup"><span data-stu-id="38b02-127">Items:</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem><span data-ttu-id="38b02-128">: Управляет списком локальных сборок, которые будут использоваться в рабочем процессе для элементов управления (например, в редакторе выражений).</span><span class="sxs-lookup"><span data-stu-id="38b02-128">: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState><span data-ttu-id="38b02-129">: Указывает, находится ли конструктор в состоянии только для чтения.</span><span class="sxs-lookup"><span data-stu-id="38b02-129">: Indicates whether the designer is in a read-only state.</span></span>  
  
-   <xref:System.Activities.Presentation.View.Selection><span data-ttu-id="38b02-130">: Определяет коллекцию объектов, выбранных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="38b02-130">: Defines the collection of objects that are currently selected.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem><span data-ttu-id="38b02-131">:</span><span class="sxs-lookup"><span data-stu-id="38b02-131">:</span></span>  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem><span data-ttu-id="38b02-132">: Сведения о файле, который зависит от текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="38b02-132">: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="38b02-133">Службы:</span><span class="sxs-lookup"><span data-stu-id="38b02-133">Services:</span></span>  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService><span data-ttu-id="38b02-134">: Позволяет добавлять в текущий экземпляр свойства с помощью <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-134">: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.View.DesignerView><span data-ttu-id="38b02-135">: Разрешает доступ к свойствам полотна конструктора.</span><span class="sxs-lookup"><span data-stu-id="38b02-135">: Allows access to the properties of the designer canvas.</span></span>  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService><span data-ttu-id="38b02-136">: Допускает содержание элементов обновляться.</span><span class="sxs-lookup"><span data-stu-id="38b02-136">: Allows the contents of the toolbox to be updated.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService><span data-ttu-id="38b02-137">: Используется для интеграции команд конструктора (например, контекстное меню) с реализациями пользовательские службы.</span><span class="sxs-lookup"><span data-stu-id="38b02-137">: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView><span data-ttu-id="38b02-138">: Предоставляет функциональные возможности отладчика конструктора.</span><span class="sxs-lookup"><span data-stu-id="38b02-138">: Provides functionality for the designer debugger.</span></span>  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService><span data-ttu-id="38b02-139">: Предоставляет доступ к диалоговому окну редактора выражений.</span><span class="sxs-lookup"><span data-stu-id="38b02-139">: Provides access to the Expression Editor dialog.</span></span>  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService><span data-ttu-id="38b02-140">: Реализует в конструкторе функциональность встроенной справки.</span><span class="sxs-lookup"><span data-stu-id="38b02-140">: Provides the designer with integrated help functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService><span data-ttu-id="38b02-141">: Предоставляет доступ к ошибкам проверки через <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-141">: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService><span data-ttu-id="38b02-142">: -Реализует внутреннюю службу для хранения и извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="38b02-142">: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="38b02-143">Эта служба является внутренним классом .NET Framework и не предназначен для внешнего использования.</span><span class="sxs-lookup"><span data-stu-id="38b02-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService><span data-ttu-id="38b02-144">: Предоставляет доступ к XAML нагрузки ошибка коллекции с помощью <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-144">: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ModelService><span data-ttu-id="38b02-145">: Используется конструктором для взаимодействия с моделью редактируемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="38b02-145">: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager><span data-ttu-id="38b02-146">: Предоставляет доступ к корню дерева элементов модели, используя <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b02-146">: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
-   <xref:System.Activities.Presentation.UndoEngine><span data-ttu-id="38b02-147">: Предоставляет отмены и возврата.</span><span class="sxs-lookup"><span data-stu-id="38b02-147">: Provides undo and redo functionality.</span></span>  
  
-   <xref:System.Activities.Presentation.Services.ViewService><span data-ttu-id="38b02-148">: Сопоставляет визуальные элементы с элементами базовой модели.</span><span class="sxs-lookup"><span data-stu-id="38b02-148">: Maps visual elements to underlying model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.ViewStateService><span data-ttu-id="38b02-149">: Сохраняет состояния представления для элементов модели.</span><span class="sxs-lookup"><span data-stu-id="38b02-149">: Stores view states for model items.</span></span>  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService><span data-ttu-id="38b02-150">: Используется для настройки поведения пользовательского интерфейса виртуального контейнера.</span><span class="sxs-lookup"><span data-stu-id="38b02-150">: Used to customize the virtual container UI behavior.</span></span>  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService><span data-ttu-id="38b02-151">: Используется для регистрации и отмены регистрации делегатов для уведомлений о событиях.</span><span class="sxs-lookup"><span data-stu-id="38b02-151">: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="38b02-152">Кроме того, позволяет задавать владельца окна.</span><span class="sxs-lookup"><span data-stu-id="38b02-152">Also allows a window owner to be set.</span></span>
