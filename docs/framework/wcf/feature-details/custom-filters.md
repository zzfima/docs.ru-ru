---
title: "Настраиваемые фильтры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: c9d0c81d715b2e876fe8144d4cff198f3321a22e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="custom-filters"></a><span data-ttu-id="25a3e-102">Настраиваемые фильтры</span><span class="sxs-lookup"><span data-stu-id="25a3e-102">Custom Filters</span></span>
<span data-ttu-id="25a3e-103">Пользовательские фильтры позволяют определять логику сопоставления, которую невозможно определить с помощью фильтров системных сообщений.</span><span class="sxs-lookup"><span data-stu-id="25a3e-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="25a3e-104">Например, можно создать пользовательский фильтр, который хэширует определенный элемент сообщений, а затем выполняет проверку значения, чтобы определить значение, которое возвращается фильтром (true или false).</span><span class="sxs-lookup"><span data-stu-id="25a3e-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="25a3e-105">Реализация</span><span class="sxs-lookup"><span data-stu-id="25a3e-105">Implementation</span></span>  
 <span data-ttu-id="25a3e-106">Пользовательский фильтр является реализацией абстрактного базового класса <xref:System.ServiceModel.Dispatcher.MessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="25a3e-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="25a3e-107">При реализации пользовательского фильтра конструктор может, если необходимо, принять один строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="25a3e-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="25a3e-108">Этот параметр содержит данные о конфигурации, которые передаются конструктору MessageFilter для предоставления значений и настроек, необходимых фильтру во время выполнения для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="25a3e-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="25a3e-109">Например, их можно использовать, чтобы указать значение, поиск которого в оцениваемом сообщении выполняет фильтр.</span><span class="sxs-lookup"><span data-stu-id="25a3e-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="25a3e-110">В следующем примере показана базовая реализация настраиваемого фильтра сообщений, принимающего строковый параметр:</span><span class="sxs-lookup"><span data-stu-id="25a3e-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="25a3e-111">В фактической реализации метод match содержит логику, которая будет выполняться проверка сообщения, чтобы определить, если этот фильтр сообщений должен вернуть **true** или **false**.</span><span class="sxs-lookup"><span data-stu-id="25a3e-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="25a3e-112">Производительность</span><span class="sxs-lookup"><span data-stu-id="25a3e-112">Performance</span></span>  
 <span data-ttu-id="25a3e-113">Реализуя пользовательский фильтр, важно принять во внимание максимальное время, которое может потребоваться фильтру для завершения обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="25a3e-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="25a3e-114">Поскольку сообщение может обрабатываться несколькими фильтрами перед тем, как будет найдено совпадение, важно убедиться, что время ожидания клиентского запроса не завершится раньше, чем сообщение смогут обработать все фильтры.</span><span class="sxs-lookup"><span data-stu-id="25a3e-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="25a3e-115">Вследствие этого пользовательский фильтр должен содержать только код, необходимый для обработки содержимого или атрибутов сообщения, чтобы определить его соответствие условиям фильтра.</span><span class="sxs-lookup"><span data-stu-id="25a3e-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="25a3e-116">В целом, при реализации пользовательского фильтра следует избегать следующих действий.</span><span class="sxs-lookup"><span data-stu-id="25a3e-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
-   <span data-ttu-id="25a3e-117">Ввод-вывод, например сохранение данных на диск или в базу данных.</span><span class="sxs-lookup"><span data-stu-id="25a3e-117">IO, such as saving data to disk or to a database.</span></span>  
  
-   <span data-ttu-id="25a3e-118">Ненужная обработка, например циклический проход по многочисленным записям в документе.</span><span class="sxs-lookup"><span data-stu-id="25a3e-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
-   <span data-ttu-id="25a3e-119">Блокировка операций, например вызовы, которые предусматривают блокировку совместно используемых ресурсов или поиск по базе данных.</span><span class="sxs-lookup"><span data-stu-id="25a3e-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="25a3e-120">Перед использованием пользовательского фильтра в рабочей среде следует провести тесты производительности для определения средней продолжительности времени, в течение которого фильтр обрабатывает сообщение.</span><span class="sxs-lookup"><span data-stu-id="25a3e-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="25a3e-121">В сумме со средним временем обработки для других фильтров, используемых в таблице фильтров, это позволит достаточно точно определить максимальное значение времени ожидания, которое необходимо задать в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="25a3e-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="25a3e-122">Использование</span><span class="sxs-lookup"><span data-stu-id="25a3e-122">Usage</span></span>  
 <span data-ttu-id="25a3e-123">Чтобы использовать пользовательский фильтр со службой маршрутизации, необходимо добавить его в таблицу фильтров, указав новую запись фильтра с типом «Пользовательский», полное имя типа фильтра сообщений и имя сборки.</span><span class="sxs-lookup"><span data-stu-id="25a3e-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="25a3e-124">Как и в случае с другими фильтрами MessageFilters, можно указать строковые данные filterData, передаваемые конструктору пользовательского фильтра.</span><span class="sxs-lookup"><span data-stu-id="25a3e-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="25a3e-125">В следующем примере показывается использование пользовательского фильтра при работе со службой маршрутизации:</span><span class="sxs-lookup"><span data-stu-id="25a3e-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"   
            customType="CustomAssembly.MyMessageFilter,   
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```
