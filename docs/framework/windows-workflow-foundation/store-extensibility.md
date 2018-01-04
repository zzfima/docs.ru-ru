---
title: "Расширяемость хранилища"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e269f485da16bcf3669bb8cb32396fad2875ca89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="store-extensibility"></a><span data-ttu-id="318aa-102">Расширяемость хранилища</span><span class="sxs-lookup"><span data-stu-id="318aa-102">Store Extensibility</span></span>
<span data-ttu-id="318aa-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> позволяет пользователям повышать уровень относящихся к приложению пользовательских свойств, которые могут использоваться для создания запросов к экземплярам в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="318aa-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="318aa-104">Благодаря действию по повышению уровня свойства значение становится доступным в специальном представлении в базе данных.</span><span class="sxs-lookup"><span data-stu-id="318aa-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="318aa-105">Свойства с повышенным уровнем (т.е. свойства, которые могут использоваться в пользовательских запросах), могут относиться к простым типам, например к Int64, Guid, String, DateTime или к сериализованному двоичному типу (byte[]).</span><span class="sxs-lookup"><span data-stu-id="318aa-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>  
  
 <span data-ttu-id="318aa-106">Класс <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> содержит метод <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A>, который может использоваться для повышения уровня свойства, чтобы его можно было использовать в запросах.</span><span class="sxs-lookup"><span data-stu-id="318aa-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="318aa-107">Ниже приведен подробный пошаговый пример расширения хранилища.</span><span class="sxs-lookup"><span data-stu-id="318aa-107">The following example is an end-to-end example of store extensibility.</span></span>  
  
1.  <span data-ttu-id="318aa-108">В данном образце сценария приложение обработки документов содержит рабочие процессы, в каждом из которых для обработки документов применяются пользовательские действия.</span><span class="sxs-lookup"><span data-stu-id="318aa-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="318aa-109">Эти рабочие процессы содержат набор переменных состояния, которые необходимо сделать доступными для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="318aa-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="318aa-110">Для этого приложение обработки документов предоставляет расширение экземпляра типа <xref:System.Activities.Persistence.PersistenceParticipant>, используемое действиями для предоставления переменных состояния.</span><span class="sxs-lookup"><span data-stu-id="318aa-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
    ```  
  
2.  <span data-ttu-id="318aa-111">Затем к узлу добавляется новое расширение.</span><span class="sxs-lookup"><span data-stu-id="318aa-111">The new extension is then added to the host.</span></span>  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
    ```  
  
     <span data-ttu-id="318aa-112">Дополнительные сведения о добавлении участника настраиваемой сохраняемости см. в разделе [участников сохраняемости](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) образца.</span><span class="sxs-lookup"><span data-stu-id="318aa-112">For more details about adding a custom persistence participant, see the [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) sample.</span></span>  
  
3.  <span data-ttu-id="318aa-113">Настраиваемые действия в приложение обработки Документов заполняют различные поля состояния в **Execute** метод.</span><span class="sxs-lookup"><span data-stu-id="318aa-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>  
  
    ```  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
    ```  
  
4.  <span data-ttu-id="318aa-114">Когда экземпляр рабочего процесса достигает точки сохраняемости **CollectValues** метод **DocumentStatusExtension** участник сохраняемости сохраняет данные свойства в данных сохраняемости Коллекция.</span><span class="sxs-lookup"><span data-stu-id="318aa-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");  
  
        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)  
        {  
            readWriteValues = new Dictionary<XName, object>();  
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);  
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);  
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);  
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);  
  
            writeOnlyValues = null;  
        }  
        // ...  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="318aa-115">Эти свойства передаются в **SqlWorkflowInstanceStore** платформой сохраняемости через **SaveWorkflowCommand.InstanceData** коллекции.</span><span class="sxs-lookup"><span data-stu-id="318aa-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>  
  
5.  <span data-ttu-id="318aa-116">Приложение обработки Документов инициализирует хранилище экземпляров рабочих процессов SQL и вызывает **Promote** для повышения уровня этих данных.</span><span class="sxs-lookup"><span data-stu-id="318aa-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>  
  
    ```  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
  
    List<XName> variantProperties = new List<XName>()   
    {   
        xNS.GetName("UserName"),   
        xNS.GetName("ApprovalStatus"),   
        xNS.GetName("DocumentId"),   
        xNS.GetName("LastModifiedTime")   
    };  
  
    store.Promote("DocumentStatus", variantProperties, null);  
    ```  
  
     <span data-ttu-id="318aa-117">На основе этих сведений рекламной акции **SqlWorkflowInstanceStore** помещает свойства данных в столбцах [InstancePromotedProperties](#InstancePromotedProperties) представления.</span><span class="sxs-lookup"><span data-stu-id="318aa-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>
  
6.  <span data-ttu-id="318aa-118">Чтобы создать запрос к подмножеству данных из таблицы повышения уровня, приложение обработки данных добавляет пользовательское представление к представлению повышения уровня.</span><span class="sxs-lookup"><span data-stu-id="318aa-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>  
  
    ```  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
    ```  
  
##  <a name="InstancePromotedProperties"></a><span data-ttu-id="318aa-119">Представления [System.Activities.DurableInstancing.InstancePromotedProperties]</span><span class="sxs-lookup"><span data-stu-id="318aa-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>  
  
|<span data-ttu-id="318aa-120">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="318aa-120">Column Name</span></span>|<span data-ttu-id="318aa-121">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="318aa-121">Column Type</span></span>|<span data-ttu-id="318aa-122">Описание</span><span class="sxs-lookup"><span data-stu-id="318aa-122">Description</span></span>|  
|-----------------|-----------------|-----------------|  
|<span data-ttu-id="318aa-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="318aa-123">InstanceId</span></span>|<span data-ttu-id="318aa-124">GUID</span><span class="sxs-lookup"><span data-stu-id="318aa-124">GUID</span></span>|<span data-ttu-id="318aa-125">Экземпляр рабочего процесса, которому принадлежит это повышение уровня.</span><span class="sxs-lookup"><span data-stu-id="318aa-125">The workflow instance that this promotion belongs to.</span></span>|  
|<span data-ttu-id="318aa-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="318aa-126">PromotionName</span></span>|<span data-ttu-id="318aa-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="318aa-127">nvarchar(400)</span></span>|<span data-ttu-id="318aa-128">Имя самого продвижения.</span><span class="sxs-lookup"><span data-stu-id="318aa-128">The name of the promotion itself.</span></span>|  
|<span data-ttu-id="318aa-129">Value1, Value2, Value3,..,Value32</span><span class="sxs-lookup"><span data-stu-id="318aa-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="318aa-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="318aa-130">sql_variant</span></span>|<span data-ttu-id="318aa-131">Значение самого свойства, уровень которого повышен.</span><span class="sxs-lookup"><span data-stu-id="318aa-131">The value of the promoted property itself.</span></span> <span data-ttu-id="318aa-132">Большинство примитивных типов данных SQL, за исключением больших двоичных объектов BLOB и строк длиной более 8000 байт, помещается в sql_variant.</span><span class="sxs-lookup"><span data-stu-id="318aa-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|  
|<span data-ttu-id="318aa-133">Value33, Value34, Value35, …, Value64</span><span class="sxs-lookup"><span data-stu-id="318aa-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="318aa-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="318aa-134">varbinary(max)</span></span>|<span data-ttu-id="318aa-135">Значение свойств повышаемого уровня, явно объявленных, как varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="318aa-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
