---
title: "Как создать настраиваемое хранилище экземпляров | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Как создать настраиваемое хранилище экземпляров
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] содержит <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> \- хранилище экземпляров SQL Server, которое используется для сохранения данных рабочих процессов.  Если приложению необходимо сохранить данные рабочего процесса в другой среде передачи, например базе данных или файловой системе, вы можете создать настраиваемое хранилище экземпляров.  Пользовательское хранилище экземпляров создается путем расширения абстрактного класса <xref:System.Runtime.DurableInstancing.InstanceStore> и реализации методов, которые необходимы для реализации.  Полную реализацию пользовательского хранилища экземпляров см. в образце [Процесс корпоративных закупок](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md).  
  
## Реализация метода BeginTryCommand  
 <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> отправляется в хранилище экземпляров подсистемой сохраняемости.  Тип параметра `command` указывает, какая команда выполняется. Этот параметр может быть следующих типов:  
  
-   <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>. Подсистема сохраняемости отправляет эту команду в хранилище экземпляров, когда рабочий процесс должен были сохранен в среде хранения.  Сведения о сохраняемости рабочего процесса передаются методу в участнике <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> параметра `command`.  
  
-   <xref:System.Activities.DurableInstancing.LoadWorkflowCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров при вызове рабочего процесса из среды хранения.  Идентификатор экземпляра рабочего процесса, который требуется загрузить, предоставляется методу в параметре `instanceId` свойства <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> параметра `context`.  
  
-   <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров, когда <xref:System.ServiceModel.Activities.WorkflowServiceHost> следует зарегистрировать в качестве владельца блокировки.  Идентификатор экземпляра текущего рабочего процесса должен быть передан в хранилище экземпляров с помощью метода <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> в параметре `context`.  
  
     В следующем фрагменте кода показано, как реализовать команду CreateWorkflowOwner, чтобы назначить явного владельца блокировки.  
  
    ```  
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");  
    ...  
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()  
    {  
        InstanceOwnerMetadata =  
        {  
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },  
        }  
    };  
    InstanceHandle ownerHandle = store.CreateInstanceHandle();  
    store.DefaultInstanceOwner = store.Execute(  
                                   ownerHandle,  
                                   createCommand,  
                                   TimeSpan.FromSeconds(30)).InstanceOwner;  
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });  
  
    ```  
  
-   <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров, если идентификатор экземпляра владельца блокировки может быть удален из хранилища экземпляров.  Как и в случае с <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, идентификатор владельца блокировки должен быть предоставлен приложением.  
  
     В следующем фрагменте кода показано, как с помощью <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand> освободить блокировку.  
  
    ```  
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)  
    {  
        handle.Free();  
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);  
        try  
        {  
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.  
            Thread.Sleep(10000);  
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));  
        }  
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }  
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }  
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }  
        catch (Exception ex) { Log.Inform(ex.Message); }  
        finally  
        {  
            handle.Free();  
            store.DefaultInstanceOwner = null;  
        }  
    }  
  
    ```  
  
     Приведенный выше метод должен быть вызван в блоке try\/catch при запуске экземпляра дочернего действия.  
  
    ```  
    try  
    {  
        childInstance.Run();  
    }  
    catch (Exception)  
    {  
        throw ;  
    }  
    finally  
    {  
        FreeHandleAndDeleteOwner(store, ownerHandle);  
    }  
  
    ```  
  
-   <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров, когда экземпляр рабочего процесса необходимо загрузить с помощью ключа экземпляра рабочего процесса.  Идентификатор ключа экземпляра может быть указан с помощью параметра <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> команды.  
  
-   <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров для извлечения параметров активации сохраненных рабочих процессов для создания узла рабочего процесса, который затем может загружать рабочие процессы.  Эта команда отправляется подсистемой в ответ на вызов хранилищем экземпляров <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> для узла, когда она выполняет поиск экземпляра, который можно активировать.  Хранилище экземпляров должно быть опрошено, чтобы определить, есть ли рабочие процессы, которые можно активировать.  
  
-   <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>. Механизм сохраняемости отправляет эту команду в хранилище экземпляров для загрузки запускаемых экземпляров рабочих процессов.  Эта команда отправляется подсистемой в ответ на вызов хранилищем экземпляров <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> для узла, когда она выполняет поиск экземпляра, который можно выполнить.  Хранилище экземпляров должно сделать запрос рабочих процессов, которые можно выполнить.  Следующий фрагмент кода демонстрирует опрос в хранилище экземпляров рабочих процессов, которые можно выполнить или активировать.  
  
    ```  
    public void PollForEvents()  
    {  
        InstanceOwner[] storeOwners = this.GetInstanceOwners();  
  
        foreach (InstanceOwner owner in storeOwners)  
        {  
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))  
            {  
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))  
                {  
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivable);  
                    if (hasRunnable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))  
                {  
                   bool hasActivable = GetActivableEvents(this.StoreId, owner.InstanceOwnerId);  
                   if (hasActivable)  
                    {  
                        this.SignalEvent(ppEvent, owner);  
                    }  
                    else  
                    {  
                        this.ResetEvent(ppEvent, owner);  
                    }  
                }  
            }  
        }  
    }  
  
    ```  
  
     В предыдущем фрагменте кода хранилище экземпляров запрашивает доступные события и проверяет каждое из них, определяя, является ли оно событием <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>.  Если событие обнаружено, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> вызывается для подачи сигнала узлу для отправки команды в хранилище экземпляров.  Следующий фрагмент кода демонстрирует реализацию обработчика события для этой команды.  
  
    ```  
    If (command is TryLoadRunnableWorkflowCommand)  
    {  
        Owner owner;  
        CheckOwner(context, command.Name, out owner);                          
        // Checking instance.Owner is like an InstanceLockQueryResult.  
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));  
  
        XName ownerService = null;  
        InstanceValue value;  
        Instance runnableInstance = default(Instance);  
        bool foundRunnableInstance = false;  
  
        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);  
        if (value != null && value.Value is XName)  
        {  
            ownerService = (XName)value.Value;  
        }  
  
        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)  
        {  
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)  
            {  
                continue;  
            }  
  
            if (ownerService != null)  
            {  
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);  
                if (value == null || ((XName)value.Value) != ownerService)  
                {  
                    continue;  
                }  
            }  
  
            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);  
            if (value != null && value.Value != null && value.Value is string)  
            {  
                continue;  
            }  
  
            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);  
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")  
            {  
                runnableInstance = instance.Value;  
                foundRunnableInstance = true;  
            }  
  
            if (!foundRunnableInstance)  
            {  
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);  
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)  
                {                          
                    runnableInstance = instance.Value;  
                    foundRunnableInstance = true;  
                }  
            }  
  
            if (foundRunnableInstance)  
            {  
                runnableInstance.LockVersion++;  
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;  
                MemoryStore.instances[instance.Key] = runnableInstance;  
                context.BindInstance(instance.Key);  
                context.BindAcquiredLock(runnableInstance.LockVersion);  
  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();  
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)  
                {  
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)  
                {  
                    if (keyEntry.Value.Completed)  
                    {  
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                    else  
                    {  
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));  
                    }  
                }  
            }  
  
            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);  
            break;  
        }  
    }  
  
    ```  
  
     В предыдущем фрагменте кода хранилище экземпляров выполняет поиск запускаемых экземпляров.  Если экземпляр найден, он связывается с контекстом выполнения и загружается.  
  
## Использование пользовательского хранилища экземпляров  
 Чтобы реализовать пользовательское хранилище экземпляров, присвойте <xref:System.Activities.WorkflowApplication.InstanceStore%2A> экземпляр хранилища экземпляров и реализуйте метод <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>.  Подробности см. в учебнике [Как создать и запустить длительно выполняющийся рабочий процесс](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md).  
  
## Образец хранилища экземпляров  
 В следующем образце кода показана полная реализация хранилища экземпляров, взятая из образца [Процесс корпоративных закупок](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md).  Это хранилище экземпляров сохраняет данные рабочих процессов в файл с помощью XML.  
  
```  
  
using System;  
using System.Activities.DurableInstancing;  
using System.Collections.Generic;  
using System.IO;  
using System.Runtime.DurableInstancing;  
using System.Runtime.Serialization;  
using System.ServiceModel.Persistence;  
using System.Xml;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.WF.PurchaseProcess  
{  
  
    public class XmlWorkflowInstanceStore : InstanceStore  
    {  
        Guid ownerInstanceID;  
  
        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())  
        {  
  
        }  
  
        public XmlWorkflowInstanceStore(Guid id)  
        {  
            ownerInstanceID = id;  
        }  
  
        //Synchronous version of the Begin/EndTryCommand functions  
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)  
        {  
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));  
        }  
  
        //The persistence engine will send a variety of commands to the configured InstanceStore,  
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.  
        //This method is where we will handle those commands  
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)  
        {  
            IDictionary<XName, InstanceValue> data = null;  
  
            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle  
            if (command is CreateWorkflowOwnerCommand)  
            {  
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());  
            }  
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key  
            else if (command is SaveWorkflowCommand)  
            {  
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;  
                data = saveCommand.InstanceData;  
  
                Save(data);  
            }  
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle  
            else if (command is LoadWorkflowCommand)  
            {  
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
  
                try  
                {  
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))  
                    {  
                        data = LoadInstanceDataFromFile(inputStream);  
                        //load the data into the persistence Context  
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);  
                    }  
                }  
                catch (Exception exception)  
                {  
                    throw new PersistenceException(exception.Message);  
                }  
            }  
  
            return new CompletedAsyncResult<bool>(true, callback, state);  
        }  
  
        protected override bool EndTryCommand(IAsyncResult result)  
        {  
            return CompletedAsyncResult<bool>.End(result);  
        }  
  
        //Reads data from xml file and creates a dictionary based off of that.  
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)  
        {  
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();  
  
            NetDataContractSerializer s = new NetDataContractSerializer();  
  
            XmlReader rdr = XmlReader.Create(inputStream);  
            XmlDocument doc = new XmlDocument();  
            doc.Load(rdr);  
  
            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");  
            foreach (XmlElement instanceElement in instances)  
            {  
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");  
                XName key = (XName)DeserializeObject(s, keyElement);  
  
                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");  
                object value = DeserializeObject(s, valueElement);  
                InstanceValue instVal = new InstanceValue(value);  
  
                data.Add(key, instVal);  
            }  
  
            return data;  
        }  
  
        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)  
        {  
            object deserializedObject = null;  
  
            MemoryStream stm = new MemoryStream();  
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);  
            element.WriteContentTo(wtr);  
            wtr.Flush();  
            stm.Position = 0;  
  
            deserializedObject = serializer.Deserialize(stm);  
  
            return deserializedObject;  
        }  
  
        //Saves the persistence data to an xml file.  
        void Save(IDictionary<XName, InstanceValue> instanceData)  
        {  
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);  
            XmlDocument doc = new XmlDocument();  
            doc.LoadXml("<InstanceValues/>");  
  
            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)  
            {  
                XmlElement newInstance = doc.CreateElement("InstanceValue");  
  
                XmlElement newKey = SerializeObject("key", valPair.Key, doc);  
                newInstance.AppendChild(newKey);  
  
                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);  
                newInstance.AppendChild(newValue);  
  
                doc.DocumentElement.AppendChild(newInstance);  
            }  
            doc.Save(fileName);  
       }  
  
        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)  
        {  
            NetDataContractSerializer s = new NetDataContractSerializer();  
            XmlElement newElement = doc.CreateElement(elementName);  
            MemoryStream stm = new MemoryStream();  
  
            s.Serialize(stm, o);  
            stm.Position = 0;  
            StreamReader rdr = new StreamReader(stm);  
            newElement.InnerXml = rdr.ReadToEnd();  
  
            return newElement;  
        }  
    }  
}  
  
```