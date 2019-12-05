---
title: Синхронные и асинхронные операции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
ms.openlocfilehash: 143cc0f4566d86f1d42ebd11063f9af3c1ec331f
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802444"
---
# <a name="synchronous-and-asynchronous-operations"></a><span data-ttu-id="fcd31-102">Синхронные и асинхронные операции</span><span class="sxs-lookup"><span data-stu-id="fcd31-102">Synchronous and Asynchronous Operations</span></span>
<span data-ttu-id="fcd31-103">В этом разделе описывается реализация и вызов асинхронных операций службы.</span><span class="sxs-lookup"><span data-stu-id="fcd31-103">This topic discusses implementing and calling asynchronous service operations.</span></span>  
  
 <span data-ttu-id="fcd31-104">Многие приложения вызывают методы асинхронно, поскольку это позволяет приложению продолжать выполнение других операций, пока осуществляется вызов метода.</span><span class="sxs-lookup"><span data-stu-id="fcd31-104">Many applications call methods asynchronously because it enables the application to continue doing useful work while the method call runs.</span></span> <span data-ttu-id="fcd31-105">Службы и клиенты WCF (Windows Communication Foundation) могут участвовать в асинхронных вызовах операций на двух различных уровнях приложения, которые обеспечивают приложениям WCF большую гибкость для увеличения пропускной способности без ущерба для интерактивности.</span><span class="sxs-lookup"><span data-stu-id="fcd31-105">Windows Communication Foundation (WCF) services and clients can participate in asynchronous operation calls at two distinct levels of the application, which provide WCF applications even more flexibility to maximize throughput balanced against interactivity.</span></span>  
  
## <a name="types-of-asynchronous-operations"></a><span data-ttu-id="fcd31-106">Типы асинхронных операций</span><span class="sxs-lookup"><span data-stu-id="fcd31-106">Types of Asynchronous Operations</span></span>  
 <span data-ttu-id="fcd31-107">Все контракты служб в WCF не зависят от типов параметров и возвращаемых значений и используют атрибуты WCF, чтобы определить конкретный шаблон обмена сообщениями между клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="fcd31-107">All service contracts in WCF, no matter the parameters types and return values, use WCF attributes to specify a particular message exchange pattern between client and service.</span></span> <span data-ttu-id="fcd31-108">WCF автоматически направляет входящие и исходящие сообщения в соответствующую операцию службы или исполняемый код клиента.</span><span class="sxs-lookup"><span data-stu-id="fcd31-108">WCF automatically routes inbound and outbound messages to the appropriate service operation or running client code.</span></span>  
  
 <span data-ttu-id="fcd31-109">У клиента имеется только контракт службы, который задает шаблон обмена сообщениями для конкретной операции.</span><span class="sxs-lookup"><span data-stu-id="fcd31-109">The client possesses only the service contract, which specifies the message exchange pattern for a particular operation.</span></span> <span data-ttu-id="fcd31-110">Клиенты могут предложить разработчикам любую модель программирования, если соблюдается соответствующий шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="fcd31-110">Clients can offer the developer any programming model they choose, so long as the underlying message exchange pattern is observed.</span></span> <span data-ttu-id="fcd31-111">Аналогично службы могут реализовывать операции произвольным образом, пока соблюдается заданный шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="fcd31-111">So, too, can services implement operations in any manner, so long as the specified message pattern is observed.</span></span>  
  
 <span data-ttu-id="fcd31-112">Независимость контракта службы от реализации службы и клиента делает возможными следующие формы асинхронного выполнения в приложениях WCF:</span><span class="sxs-lookup"><span data-stu-id="fcd31-112">The independence of the service contract from either the service or client implementation enables the following forms of asynchronous execution in WCF applications:</span></span>  
  
- <span data-ttu-id="fcd31-113">клиенты могут вызывать операции запроса и ответа асинхронно, используя синхронный механизм обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="fcd31-113">Clients can invoke request/response operations asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="fcd31-114">службы могут реализовывать операции запроса и ответа асинхронно, используя синхронный механизм обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="fcd31-114">Services can implement a request/response operation asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="fcd31-115">обмен сообщениями может быть односторонним независимо от реализации клиента или службы.</span><span class="sxs-lookup"><span data-stu-id="fcd31-115">Message exchanges can be one-way, regardless of the implementation of the client or service.</span></span>  
  
### <a name="suggested-asynchronous-scenarios"></a><span data-ttu-id="fcd31-116">Предлагаемые асинхронные сценарии</span><span class="sxs-lookup"><span data-stu-id="fcd31-116">Suggested Asynchronous Scenarios</span></span>  
 <span data-ttu-id="fcd31-117">Асинхронный подход следует использовать при реализации операции службы, если реализация операции службы осуществляет блокирующий вызов, например операцию ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="fcd31-117">Use an asynchronous approach in a service operation implementation if the operation service implementation makes a blocking call, such as doing I/O work.</span></span> <span data-ttu-id="fcd31-118">При реализации асинхронной операции попробуйте вызывать асинхронные операции и методы, чтобы, насколько это возможно, расширить функции асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="fcd31-118">When you are in an asynchronous operation implementation, try to call asynchronous operations and methods to extend the asynchronous call path as far as possible.</span></span> <span data-ttu-id="fcd31-119">Например вызовите метод `BeginOperationTwo()` из метода `BeginOperationOne()`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-119">For example, call a `BeginOperationTwo()` from within `BeginOperationOne()`.</span></span>  
  
- <span data-ttu-id="fcd31-120">Асинхронный подход следует использовать в клиенте или вызывающем приложении в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="fcd31-120">Use an asynchronous approach in a client or calling application in the following cases:</span></span>  
  
- <span data-ttu-id="fcd31-121">Если операции вызываются из приложения промежуточного уровня.</span><span class="sxs-lookup"><span data-stu-id="fcd31-121">If you are invoking operations from a middle-tier application.</span></span> <span data-ttu-id="fcd31-122">(Дополнительные сведения о таких сценариях см. в статье о [клиентских приложениях среднего уровня](./feature-details/middle-tier-client-applications.md).)</span><span class="sxs-lookup"><span data-stu-id="fcd31-122">(For more information about such scenarios, see [Middle-Tier Client Applications](./feature-details/middle-tier-client-applications.md).)</span></span>  
  
- <span data-ttu-id="fcd31-123">Если операции вызываются на страницах ASP.NET, следует использовать асинхронные страницы.</span><span class="sxs-lookup"><span data-stu-id="fcd31-123">If you are invoking operations within an ASP.NET page, use asynchronous pages.</span></span>  
  
- <span data-ttu-id="fcd31-124">Если операции вызываются из любого однопотокового приложения, например приложения Windows Forms или WCF (Windows Presentation Foundation).</span><span class="sxs-lookup"><span data-stu-id="fcd31-124">If you are invoking operations from any application that is single threaded, such as Windows Forms or Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="fcd31-125">При использовании модели асинхронных вызовов на основе событий результирующее событие создается в потоке пользовательского интерфейса, в результате чего приложение получает возможность реагирования на действия пользователя, но при этом не требуется управлять несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="fcd31-125">When using the event-based asynchronous calling model, the result event is raised on the UI thread, adding responsiveness to the application without requiring you to handle multiple threads yourself.</span></span>  
  
- <span data-ttu-id="fcd31-126">В общем случае при выборе между синхронным и асинхронным вызовом следует выбирать асинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="fcd31-126">In general, if you have a choice between a synchronous and asynchronous call, choose the asynchronous call.</span></span>  
  
### <a name="implementing-an-asynchronous-service-operation"></a><span data-ttu-id="fcd31-127">Реализация асинхронной операции службы</span><span class="sxs-lookup"><span data-stu-id="fcd31-127">Implementing an Asynchronous Service Operation</span></span>  
 <span data-ttu-id="fcd31-128">Асинхронные операции могут быть реализованы с помощью одного из трех следующих методов:</span><span class="sxs-lookup"><span data-stu-id="fcd31-128">Asynchronous operations can be implemented by using one of the three following methods:</span></span>  
  
1. <span data-ttu-id="fcd31-129">асинхронная модель на основе задач;</span><span class="sxs-lookup"><span data-stu-id="fcd31-129">The task-based asynchronous pattern</span></span>  
  
2. <span data-ttu-id="fcd31-130">асинхронная модель на основе событий;</span><span class="sxs-lookup"><span data-stu-id="fcd31-130">The event-based asynchronous pattern</span></span>  
  
3. <span data-ttu-id="fcd31-131">асинхронная модель IAsyncResult.</span><span class="sxs-lookup"><span data-stu-id="fcd31-131">The IAsyncResult asynchronous pattern</span></span>  
  
#### <a name="task-based-asynchronous-pattern"></a><span data-ttu-id="fcd31-132">Асинхронная модель на основе задач</span><span class="sxs-lookup"><span data-stu-id="fcd31-132">Task-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="fcd31-133">Асинхронная модель на основе задач - это предпочтительный способ реализации асинхронных операций в силу его чрезвычайного удобства и простоты.</span><span class="sxs-lookup"><span data-stu-id="fcd31-133">The task-based asynchronous pattern is the preferred way to implement asynchronous operations because it is the easiest and most straight forward.</span></span> <span data-ttu-id="fcd31-134">Чтобы использовать этот метод, реализуйте операцию службы и укажите для нее тип возвращаемого значения Task\<T>, где T — это тип, возвращенный логической операцией.</span><span class="sxs-lookup"><span data-stu-id="fcd31-134">To use this method simply implement your service operation and specify a return type of Task\<T>, where T is the type returned by the logical operation.</span></span> <span data-ttu-id="fcd31-135">Например:</span><span class="sxs-lookup"><span data-stu-id="fcd31-135">For example:</span></span>  
  
```csharp  
public class SampleService:ISampleService   
{   
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)   
   {   
      return Task<string>.Factory.StartNew(() =>   
      {   
         return msg;   
      });   
   }  
   // ...  
}  
```  
  
 <span data-ttu-id="fcd31-136">Операция SampleMethodTaskAsync возвращает значение типа Task\<string>, так как логическая операция возвращает строковое значение.</span><span class="sxs-lookup"><span data-stu-id="fcd31-136">The SampleMethodTaskAsync operation returns Task\<string> because the logical operation returns a string.</span></span> <span data-ttu-id="fcd31-137">Дополнительные сведения об асинхронной модели на основе задач см. в [этой статье](https://go.microsoft.com/fwlink/?LinkId=232504).</span><span class="sxs-lookup"><span data-stu-id="fcd31-137">For more information about the task-based asynchronous pattern, see [The Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=232504).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="fcd31-138">При использовании асинхронной модели на основе задач может быть вызван объект T:System.AggregateException в случае возникновения исключения во время ожидания завершения операции.</span><span class="sxs-lookup"><span data-stu-id="fcd31-138">When using the task-based asynchronous pattern, a T:System.AggregateException may be thrown if an exception occurs while waiting on the completion of the operation.</span></span> <span data-ttu-id="fcd31-139">Это исключение может возникнуть на стороне клиента или службы</span><span class="sxs-lookup"><span data-stu-id="fcd31-139">This exception may occur on the client or services</span></span>  
  
#### <a name="event-based-asynchronous-pattern"></a><span data-ttu-id="fcd31-140">Асинхронная модель на основе событий</span><span class="sxs-lookup"><span data-stu-id="fcd31-140">Event-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="fcd31-141">Служба, поддерживающая асинхронную модель на основе событий, будет содержать одну или несколько операций с именем MethodNameAsync.</span><span class="sxs-lookup"><span data-stu-id="fcd31-141">A service that supports the Event-based Asynchronous Pattern will have one or more operations named MethodNameAsync.</span></span> <span data-ttu-id="fcd31-142">Эти методы могут копировать синхронные версии, выполняющие ту же операцию в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="fcd31-142">These methods may mirror synchronous versions, which perform the same operation on the current thread.</span></span> <span data-ttu-id="fcd31-143">Этот класс также может содержать событие MethodNameCompleted, а также метод MethodNameAsyncCancel (или просто CancelAsync).</span><span class="sxs-lookup"><span data-stu-id="fcd31-143">The class may also have a MethodNameCompleted event and it may have a MethodNameAsyncCancel (or simply CancelAsync) method.</span></span> <span data-ttu-id="fcd31-144">Клиент, вызывающий операцию, определяет обработчик событий, вызываемый после завершения операции.</span><span class="sxs-lookup"><span data-stu-id="fcd31-144">A client wishing to call the operation will define an event handler to be called when the operation completes,</span></span>  
  
 <span data-ttu-id="fcd31-145">В следующем фрагменте кода показано объявление асинхронных операций с помощью асинхронной модели на основе событий.</span><span class="sxs-lookup"><span data-stu-id="fcd31-145">The following code snippet illustrates how to declare asynchronous operations using the event-based asynchronous pattern.</span></span>  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 <span data-ttu-id="fcd31-146">Дополнительные сведения об асинхронной модели на основе событий см. в [этой статье](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fcd31-146">For more information about the Event-based Asynchronous Pattern, see [The Event-Based Asynchronous Pattern](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
#### <a name="iasyncresult-asynchronous-pattern"></a><span data-ttu-id="fcd31-147">Асинхронная модель IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="fcd31-147">IAsyncResult Asynchronous Pattern</span></span>  
 <span data-ttu-id="fcd31-148">Операцию службы можно реализовать асинхронно с помощью .NET Framework шаблона асинхронного программирования и пометить метод `<Begin>` свойством <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>, для которого задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-148">A service operation can be implemented in an asynchronous fashion using the .NET Framework asynchronous programming pattern and marking the `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true`.</span></span> <span data-ttu-id="fcd31-149">В этом случае асинхронная операция доступна в метаданных так же, как и синхронная операция: она предоставляется в виде одной операции с сообщением запроса и согласованным с ним сообщением ответа.</span><span class="sxs-lookup"><span data-stu-id="fcd31-149">In this case, the asynchronous operation is exposed in metadata in the same form as a synchronous operation: It is exposed as a single operation with a request message and a correlated response message.</span></span> <span data-ttu-id="fcd31-150">В этом случае имеется возможность выбора одной из двух моделей программирования клиента.</span><span class="sxs-lookup"><span data-stu-id="fcd31-150">Client programming models then have a choice.</span></span> <span data-ttu-id="fcd31-151">Этот шаблон может быть представлен в них в виде синхронной или асинхронной операции, поскольку при вызове службы имеет место обмен сообщениями "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="fcd31-151">They can represent this pattern as a synchronous operation or as an asynchronous one, so long as when the service is invoked a request-response message exchange takes place.</span></span>  
  
 <span data-ttu-id="fcd31-152">В целом в связи с асинхронной природой систем полагаться на потоки не следует.</span><span class="sxs-lookup"><span data-stu-id="fcd31-152">In general, with the asynchronous nature of the systems, you should not take a dependency on the threads.</span></span>  <span data-ttu-id="fcd31-153">Самый надежный способ передачи данных на различные этапы обработки диспетчеризации операций - это использование расширений.</span><span class="sxs-lookup"><span data-stu-id="fcd31-153">The most reliable way of passing data to various stages of operation dispatch processing is to use extensions.</span></span>  
  
 <span data-ttu-id="fcd31-154">Пример такой реализации можно изучить в статье [Практическое руководство. Асинхронная реализация операции службы](how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="fcd31-154">For an example, see [How to: Implement an Asynchronous Service Operation](how-to-implement-an-asynchronous-service-operation.md).</span></span>  
  
 <span data-ttu-id="fcd31-155">Чтобы определить операцию контракта `X`, которая выполняется асинхронно независимо от того, как она вызывается в клиентском приложении, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fcd31-155">To define a contract operation `X` that is executed asynchronously regardless of how it is called in the client application:</span></span>  
  
- <span data-ttu-id="fcd31-156">Определите два метода, используя шаблон `BeginOperation` и `EndOperation`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-156">Define two methods using the pattern `BeginOperation` and `EndOperation`.</span></span>  
  
- <span data-ttu-id="fcd31-157">Метод `BeginOperation` включает параметры `in` и `ref` для операции и возвращает значение типа <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-157">The `BeginOperation` method includes `in` and `ref` parameters for the operation and returns an <xref:System.IAsyncResult> type.</span></span>  
  
- <span data-ttu-id="fcd31-158">Метод `EndOperation` включает параметр <xref:System.IAsyncResult>, а также параметры `out` и `ref`, и возвращает результат возвращаемого типа операции.</span><span class="sxs-lookup"><span data-stu-id="fcd31-158">The `EndOperation` method includes an <xref:System.IAsyncResult> parameter as well as the `out` and `ref` parameters and returns the operations return type.</span></span>  
  
 <span data-ttu-id="fcd31-159">См., например, следующий метод.</span><span class="sxs-lookup"><span data-stu-id="fcd31-159">For example, see the following method.</span></span>  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 <span data-ttu-id="fcd31-160">Для создания асинхронной операции эти два метода должны иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="fcd31-160">To create an asynchronous operation, the two methods would be:</span></span>  
  
```csharp  
[OperationContract(AsyncPattern=true)]
IAsyncResult BeginDoWork(string data,
                         ref string inout,
                         AsyncCallback callback,
                         object state);
int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>
Function BeginDoWork(ByVal data As String, _
                     ByRef inout As String, _
                     ByVal callback As AsyncCallback, _
                     ByVal state As Object) As IAsyncResult
Function EndDoWork(ByRef inout As String, ByRef outonly As String, ByVal result As IAsyncResult) As Integer  
```  
  
> [!NOTE]
> <span data-ttu-id="fcd31-161">Атрибут <xref:System.ServiceModel.OperationContractAttribute> применяется только к методу `BeginDoWork`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-161">The <xref:System.ServiceModel.OperationContractAttribute> attribute is applied only to the `BeginDoWork` method.</span></span> <span data-ttu-id="fcd31-162">В получаемом контракте имеется одна операция WSDL с именем `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-162">The resulting contract has one WSDL operation named `DoWork`.</span></span>  
  
### <a name="client-side-asynchronous-invocations"></a><span data-ttu-id="fcd31-163">Асинхронные вызовы на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="fcd31-163">Client-Side Asynchronous Invocations</span></span>  
 <span data-ttu-id="fcd31-164">Клиентское приложение WCF может использовать любую из трех описанных выше моделей асинхронных вызовов.</span><span class="sxs-lookup"><span data-stu-id="fcd31-164">A WCF client application can use any of three asynchronous calling models described previously</span></span>  
  
 <span data-ttu-id="fcd31-165">При использовании модели на основе задач просто вызовите операцию, используя ключевое слово «await», как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="fcd31-165">When using the task-based model, simply call the operation using the await keyword as shown in the following code snippet.</span></span>  
  
```csharp  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 <span data-ttu-id="fcd31-166">Использование асинхронной модели на основе событий требует добавления обработчика событий для получения уведомлений об ответе. Результирующее событие будет создано в потоке пользовательского интерфейса автоматически.</span><span class="sxs-lookup"><span data-stu-id="fcd31-166">Using the event-based asynchronous pattern only requires adding an event handler to receive a notification of the response -- and the resulting event is raised on the user interface thread automatically.</span></span> <span data-ttu-id="fcd31-167">Чтобы воспользоваться этим подходом, укажите параметры командной строки **/async** и **/tcv:Version35** в [служебном средстве ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fcd31-167">To use this approach, specify both the **/async** and **/tcv:Version35** command options with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 <span data-ttu-id="fcd31-168">В такой конфигурации служебная программа Svcutil.exe создает класс клиента WCF с инфраструктурой событий, которая позволяет вызывающему приложению реализовать и присвоить обработчик событий, который получает ответ и выполняет соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="fcd31-168">When this is done, Svcutil.exe generates a WCF client class with the event infrastructure that enables the calling application to implement and assign an event handler to receive the response and take the appropriate action.</span></span> <span data-ttu-id="fcd31-169">Полный пример такой реализации см. в статье [Практическое руководство. Асинхронный вызов операций службы](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="fcd31-169">For a complete example, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
 <span data-ttu-id="fcd31-170">Однако асинхронная модель, основанная на событиях, доступна только в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="fcd31-170">The event-based asynchronous model, however, is only available in .NET Framework 3.5.</span></span> <span data-ttu-id="fcd31-171">Кроме того, он не поддерживается даже в .NET Framework 3,5, когда канал клиента WCF создается с помощью <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-171">In addition, it is not supported even in .NET Framework 3.5 when a WCF client channel is created by using a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fcd31-172">Для асинхронного вызова операций в объектах клиентского канала WCF необходимо использовать объекты <xref:System.IAsyncResult?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-172">With WCF client channel objects, you must use <xref:System.IAsyncResult?displayProperty=nameWithType> objects to invoke your operations asynchronously.</span></span> <span data-ttu-id="fcd31-173">Чтобы воспользоваться этим подходом, укажите параметр командной строки **/async** в [служебном средстве ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fcd31-173">To use this approach, specify the **/async** command option with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async   
```  
  
 <span data-ttu-id="fcd31-174">В результате будет создан контракт службы, в котором каждая операция моделируется в виде метода `<Begin>`, где свойство <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> имеет значение `true`, и соответствующего метода `<End>`.</span><span class="sxs-lookup"><span data-stu-id="fcd31-174">This generates a service contract in which each operation is modeled as a `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true` and a corresponding `<End>` method.</span></span> <span data-ttu-id="fcd31-175">Полный пример с использованием <xref:System.ServiceModel.ChannelFactory%601> см. в статье [Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="fcd31-175">For a complete example using a <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
 <span data-ttu-id="fcd31-176">В любом случае приложения могут вызывать операцию асинхронно, даже если служба реализована синхронно, так же, как приложение может использовать один и тот же шаблон для асинхронного вызова и вызова локального синхронного метода.</span><span class="sxs-lookup"><span data-stu-id="fcd31-176">In either case, applications can invoke an operation asynchronously even if the service is implemented synchronously, in the same way that an application can use the same pattern to invoke asynchronously a local synchronous method.</span></span> <span data-ttu-id="fcd31-177">Способ реализации операции не важен для клиента; Когда получено ответное сообщение, его содержимое отправляется в асинхронный <ный метод клиента`End`> и клиент получает сведения.</span><span class="sxs-lookup"><span data-stu-id="fcd31-177">How the operation is implemented is not significant to the client; when the response message arrives, its content is dispatched to the client's asynchronous <`End`> method and the client retrieves the information.</span></span>  
  
### <a name="one-way-message-exchange-patterns"></a><span data-ttu-id="fcd31-178">Шаблоны одностороннего обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="fcd31-178">One-Way Message Exchange Patterns</span></span>  
 <span data-ttu-id="fcd31-179">Можно создать асинхронный шаблон обмена сообщениями, в котором односторонние операции (операции, у которых свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> имеет значение `true` и нет согласованного ответа) могут отправляться в любом направлении клиентом или службой независимо от противоположной стороны.</span><span class="sxs-lookup"><span data-stu-id="fcd31-179">You can also create an asynchronous message exchange pattern in which one-way operations (operations for which the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> is `true` have no correlated response) can be sent in either direction by the client or service independently of the other side.</span></span> <span data-ttu-id="fcd31-180">(Использует шаблон дуплексного обмена сообщениями с односторонними сообщениями.) В этом случае в контракте службы указывается односторонний обмен сообщениями, который может быть реализован либо как асинхронные вызовы, либо как несоответствующие реализации.</span><span class="sxs-lookup"><span data-stu-id="fcd31-180">(This uses the duplex message exchange pattern with one-way messages.) In this case, the service contract specifies a one-way message exchange that either side can implement as asynchronous calls or implementations, or not, as appropriate.</span></span> <span data-ttu-id="fcd31-181">Обычно, если контракт определяет односторонний обмен сообщениями, реализации бывают преимущественно асинхронными, поскольку после отправки сообщения приложение не дожидается ответа и продолжает выполнять другие операции.</span><span class="sxs-lookup"><span data-stu-id="fcd31-181">Generally, when the contract is an exchange of one-way messages, the implementations can largely be asynchronous because once a message is sent the application does not wait for a reply and can continue doing other work.</span></span>  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a><span data-ttu-id="fcd31-182">Асинхронные клиенты на основе событий и контракты сообщений</span><span class="sxs-lookup"><span data-stu-id="fcd31-182">Event-based Asynchronous Clients and Message Contracts</span></span>  
 <span data-ttu-id="fcd31-183">Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-183">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="fcd31-184">Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-184">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="fcd31-185">Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, следует использовать параметр командной строки **/messageContract**.</span><span class="sxs-lookup"><span data-stu-id="fcd31-185">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the **/messageContract** command option.</span></span> <span data-ttu-id="fcd31-186">При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fcd31-186">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="fcd31-187">Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="fcd31-187">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd31-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcd31-188">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
