---
title: Расширяемость хранилища
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 46c1ea40925a5c79180171da9a705d7e6b7c8b89
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703288"
---
# <a name="store-extensibility"></a>Расширяемость хранилища

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> позволяет пользователям повышать уровень относящихся к приложению пользовательских свойств, которые могут использоваться для создания запросов к экземплярам в базе данных сохраняемости. Благодаря действию по повышению уровня свойства значение становится доступным в специальном представлении в базе данных. Свойства с повышенным уровнем (т.е. свойства, которые могут использоваться в пользовательских запросах), могут относиться к простым типам, например к Int64, Guid, String, DateTime или к сериализованному двоичному типу (byte[]).

Класс <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> содержит метод <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A>, который может использоваться для повышения уровня свойства, чтобы его можно было использовать в запросах. Ниже приведен подробный пошаговый пример расширения хранилища.

1. В данном образце сценария приложение обработки документов содержит рабочие процессы, в каждом из которых для обработки документов применяются пользовательские действия. Эти рабочие процессы содержат набор переменных состояния, которые необходимо сделать доступными для конечных пользователей. Для этого приложение обработки документов предоставляет расширение экземпляра типа <xref:System.Activities.Persistence.PersistenceParticipant>, используемое действиями для предоставления переменных состояния.

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. Затем к узлу добавляется новое расширение.

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     Дополнительные сведения о добавлении нестандартного участника сохраняемости см. в разделе [участников сохраняемости](persistence-participants.md) образца.

3. Настраиваемые действия в приложение обработки Документов заполняют различные поля состояния в **Execute** метод.

    ```csharp
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

4. Когда экземпляр рабочего процесса достигает точки сохраняемости, **CollectValues** метод **DocumentStatusExtension** участника сохраняемости сохраняет эти свойства в данных сохраняемости Коллекция.

    ```csharp
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
    > Все эти свойства передаются **SqlWorkflowInstanceStore** платформой сохраняемости через **SaveWorkflowCommand.InstanceData** коллекции.

5. Приложение обработки Документов инициализирует Store экземпляра рабочего процесса SQL и вызывает **Promote** способ повышения уровня этих данных.

    ```csharp
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

    На основании этой информации продвижение **SqlWorkflowInstanceStore** помещает свойства данных в столбцах [InstancePromotedProperties](#InstancePromotedProperties) представления.

6. Чтобы создать запрос к подмножеству данных из таблицы повышения уровня, приложение обработки данных добавляет пользовательское представление к представлению повышения уровня.

    ```sql
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

## <a name="InstancePromotedProperties"></a> Представление [System.Activities.DurableInstancing.InstancePromotedProperties]

|Имя столбца|Тип столбца|Описание|
|-----------------|-----------------|-----------------|
|InstanceId|GUID|Экземпляр рабочего процесса, которому принадлежит это повышение уровня.|
|PromotionName|nvarchar(400)|Имя самого продвижения.|
|Value1, Value2, Value3,..,Value32|sql_variant|Значение самого свойства, уровень которого повышен. Большинство примитивных типов данных SQL, за исключением больших двоичных объектов BLOB и строк длиной более 8000 байт, помещается в sql_variant.|
|Value33, Value34, Value35, …, Value64|varbinary(max)|Значение свойств повышаемого уровня, явно объявленных, как varbinary(max).|
