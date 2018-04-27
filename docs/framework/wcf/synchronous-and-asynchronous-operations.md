---
title: Синхронные и асинхронные операции
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 123186dd5f0d63693c04c0857709292ce122f918
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="synchronous-and-asynchronous-operations"></a>Синхронные и асинхронные операции
В этом разделе описывается реализация и вызов асинхронных операций службы.  
  
 Многие приложения вызывают методы асинхронно, поскольку это позволяет приложению продолжать выполнение других операций, пока осуществляется вызов метода. Службы и клиенты [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] могут участвовать в асинхронных вызовах операций на 2 различных уровнях приложения, которые обеспечивают приложениям [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] большую гибкость для максимизации пропускной способности без ущерба для интерактивности.  
  
## <a name="types-of-asynchronous-operations"></a>Типы асинхронных операций  
 Все контракты служб в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]не зависят от типов параметров и возвращаемых значений и используют атрибуты [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], чтобы определить конкретный шаблон обмена сообщениями между клиентом и службой. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] автоматически направляет входящие и исходящие сообщения в соответствующую операцию службы или исполняемый код клиента.  
  
 У клиента имеется только контракт службы, который задает шаблон обмена сообщениями для конкретной операции. Клиенты могут предложить разработчикам любую модель программирования, если соблюдается соответствующий шаблон обмена сообщениями. Аналогично службы могут реализовывать операции произвольным образом, пока соблюдается заданный шаблон обмена сообщениями.  
  
 Независимость контракта службы от реализации службы и клиента делает возможными следующие формы асинхронного выполнения в приложениях [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]:  
  
-   клиенты могут вызывать операции запроса и ответа асинхронно, используя синхронный механизм обмена сообщениями;  
  
-   службы могут реализовывать операции запроса и ответа асинхронно, используя синхронный механизм обмена сообщениями;  
  
-   обмен сообщениями может быть односторонним независимо от реализации клиента или службы.  
  
### <a name="suggested-asynchronous-scenarios"></a>Предлагаемые асинхронные сценарии  
 Асинхронный подход следует использовать при реализации операции службы, если реализация операции службы осуществляет блокирующий вызов, например операцию ввода-вывода. При реализации асинхронной операции попробуйте вызывать асинхронные операции и методы, чтобы, насколько это возможно, расширить функции асинхронного вызова. Например вызовите метод `BeginOperationTwo()` из метода `BeginOperationOne()`.  
  
-   Асинхронный подход следует использовать в клиенте или вызывающем приложении в следующих случаях.  
  
-   Если операции вызываются из приложения промежуточного уровня. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] таких сценариев, в разделе [клиентские приложения среднего уровня](../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).)  
  
-   Если операции вызываются на страницах ASP.NET, следует использовать асинхронные страницы.  
  
-   Если вы операции вызываются из любого приложения, является однопоточным, например Windows Forms или Windows Presentation Foundation (WPF). При использовании модели асинхронных вызовов на основе событий результирующее событие создается в потоке пользовательского интерфейса, в результате чего приложение получает возможность реагирования на действия пользователя, но при этом не требуется управлять несколькими потоками.  
  
-   В общем случае при выборе между синхронным и асинхронным вызовом следует выбирать асинхронный вызов.  
  
### <a name="implementing-an-asynchronous-service-operation"></a>Реализация асинхронной операции службы  
 Асинхронные операции могут быть реализованы с помощью одного из трех следующих методов:  
  
1.  асинхронная модель на основе задач;  
  
2.  асинхронная модель на основе событий;  
  
3.  асинхронная модель IAsyncResult.  
  
#### <a name="task-based-asynchronous-pattern"></a>Асинхронная модель на основе задач  
 Асинхронная модель на основе задач - это предпочтительный способ реализации асинхронных операций в силу его чрезвычайного удобства и простоты. Для использования этого метода необходимо реализовать операцию службы и определить возвращаемый тип Task\<T >, где T — тип, возвращенный логической операцией. Пример:  
  
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
  
 Операция SampleMethodTaskAsync возвращает Task\<строка >, так как логическая операция возвращает строку. Дополнительные сведения об асинхронной модели на основе задач см. в разделе [асинхронная модель на](http://go.microsoft.com/fwlink/?LinkId=232504).  
  
> [!WARNING]
>  При использовании асинхронной модели на основе задач может быть вызван объект T:System.AggregateException в случае возникновения исключения во время ожидания завершения операции. Это исключение может возникнуть на стороне клиента или службы  
  
#### <a name="event-based-asynchronous-pattern"></a>Асинхронная модель на основе событий  
 Служба, поддерживающая асинхронную модель на основе событий, будет содержать одну или несколько операций с именем MethodNameAsync. Эти методы могут копировать синхронные версии, выполняющие ту же операцию в текущем потоке. Этот класс также может содержать событие MethodNameCompleted, а также метод MethodNameAsyncCancel (или просто CancelAsync). Клиент, вызывающий операцию, определяет обработчик событий, вызываемый после завершения операции.  
  
 В следующем фрагменте кода показано объявление асинхронных операций с помощью асинхронной модели на основе событий.  
  
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
  
 Дополнительные сведения об асинхронной модели на основе событий см. в разделе [асинхронная модель](http://go.microsoft.com/fwlink/?LinkId=232515).  
  
#### <a name="iasyncresult-asynchronous-pattern"></a>Асинхронная модель IAsyncResult  
 Операцию службы можно реализовать в асинхронном виде, используя для этого асинхронную модель программирования [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] и отметив метод `<Begin>`, свойство <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> которого имеет значение `true`. В этом случае асинхронная операция доступна в метаданных так же, как и синхронная операция: она предоставляется в виде одной операции с сообщением запроса и согласованным с ним сообщением ответа. В этом случае имеется возможность выбора одной из двух моделей программирования клиента. Этот шаблон может быть представлен в них в виде синхронной или асинхронной операции, поскольку при вызове службы имеет место обмен сообщениями "запрос-ответ".  
  
 В целом в связи с асинхронной природой систем полагаться на потоки не следует.  Самый надежный способ передачи данных на различные этапы обработки диспетчеризации операций - это использование расширений.  
  
 Пример см. в разделе [как: реализация асинхронной операции службы](../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).  
  
 Чтобы определить операцию контракта `X`, которая выполняется асинхронно независимо от того, как она вызывается в клиентском приложении, выполните следующие действия:  
  
-   Определите два метода, используя шаблон `BeginOperation` и `EndOperation`.  
  
-   Метод `BeginOperation` включает параметры `in` и `ref` для операции и возвращает значение типа <xref:System.IAsyncResult>.  
  
-   Метод `EndOperation` включает параметр <xref:System.IAsyncResult>, а также параметры `out` и `ref`, и возвращает результат возвращаемого типа операции.  
  
 См., например, следующий метод.  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 Для создания асинхронной операции эти два метода должны иметь следующий вид.  
  
```csharp  
[OperationContract(AsyncPattern=true)]IAsyncResult BeginDoWork(string data,                           ref string inout,                           AsyncCallback callback,                           object state);int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>  _Function BeginDoWork(ByVal data As String, _                 ByRef inout As String, _                 ByVal callback As AsyncCallback, _                 ByVal state As Object) _As IAsyncResult Function EndDoWork(ByRef inout As String, _        ByRef outonly As String, _        ByVal result As IAsyncResult) _As Integer  
```  
  
> [!NOTE]
>  Атрибут <xref:System.ServiceModel.OperationContractAttribute> применяется только к методу `BeginDoWork`. В получаемом контракте имеется одна операция WSDL с именем `DoWork`.  
  
### <a name="client-side-asynchronous-invocations"></a>Асинхронные вызовы на стороне клиента  
 Клиентское приложение [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] может использовать одну из трех моделей асинхронных вызовов, описанных ранее  
  
 При использовании модели на основе задач просто вызовите операцию, используя ключевое слово «await», как показано в следующем фрагменте кода.  
  
```  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 Использование асинхронной модели на основе событий требует добавления обработчика событий для получения уведомлений об ответе. Результирующее событие будет создано в потоке пользовательского интерфейса автоматически. Чтобы использовать этот подход, укажите оба **/async** и **/tcv:Version35** параметры с помощью команды [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), как показано в следующих Пример.  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 Если сделать это, средство Svcutil.exe создаст класс клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] с инфраструктурой событий, которая позволяет вызывающему приложению реализовать и присвоить обработчик событий, который получает ответ и выполняет соответствующие действия. Полный пример см. в разделе [как: асинхронно вызывать операции службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 Однако асинхронная модель на основе событий доступна только в [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]. Кроме того, она не поддерживается даже в [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], если канал клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] создается с помощью <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. В случае объектов канала клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] необходимо для асинхронного вызова операций использовать объекты <xref:System.IAsyncResult?displayProperty=nameWithType>. Чтобы использовать этот подход, укажите **/async** параметра с помощью команды [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), как показано в следующем примере.  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async   
```  
  
 В результате будет создан контракт службы, в котором каждая операция моделируется в виде метода `<Begin>`, где свойство <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> имеет значение `true`, и соответствующего метода `<End>`. Полный пример использования <xref:System.ServiceModel.ChannelFactory%601>, в разделе [как: вызов операции асинхронно с помощью фабрики каналов](../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
 В любом случае приложения могут вызывать операцию асинхронно, даже если служба реализована синхронно, так же, как приложение может использовать один и тот же шаблон для асинхронного вызова и вызова локального синхронного метода. Реализация операции не имеет значения для клиента; когда приходит ответное сообщение, его содержимое передается асинхронному методу клиента <`End`>, и клиент извлекает информацию.  
  
### <a name="one-way-message-exchange-patterns"></a>Шаблоны одностороннего обмена сообщениями  
 Можно создать асинхронный шаблон обмена сообщениями, в котором односторонние операции (операции, у которых свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> имеет значение `true` и нет согласованного ответа) могут отправляться в любом направлении клиентом или службой независимо от противоположной стороны. (При этом используется шаблон дуплексного обмена сообщениями с односторонними сообщениями.) В этом случае контракт службы задает механизм одностороннего обмена сообщениями, который может реализовываться или не реализовываться в виде асинхронных вызовов на каждой из сторон по мере необходимости. Обычно, если контракт определяет односторонний обмен сообщениями, реализации бывают преимущественно асинхронными, поскольку после отправки сообщения приложение не дожидается ответа и продолжает выполнять другие операции.  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a>Асинхронные клиенты на основе событий и контракты сообщений  
 Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>. Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>.  
  
 Если вы хотите получать объект сообщения как `Result` свойства и возвращаемые значения как свойства для этого объекта, используйте **/messageContract** параметра команды. При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>. Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
