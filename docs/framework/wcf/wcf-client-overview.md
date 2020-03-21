---
title: Общие сведения о клиентах WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 7905d540e0f06dd2863cf80381210307e3021918
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183059"
---
# <a name="wcf-client-overview"></a>Общие сведения о клиентах WCF
В этом разделе описывается, что делают клиентские приложения, как настроить, создать и использовать клиента Windows Communication Foundation (WCF) и как обеспечить безопасность клиентских приложений.  
  
## <a name="using-wcf-client-objects"></a>Использование объектов клиента WCF  
 Клиентское приложение — это управляемое приложение, использующое клиентом WCF для связи с другим приложением. Для создания клиентского приложения для службы WCF требуются следующие шаги:  
  
1. Получите контракт службы, привязки и адрес для конечной точки службы.  
  
2. Создайте клиента WCF, используя эту информацию.  
  
3. Вызовите операции.  
  
4. Закройте клиентский объект WCF.  
  
 В последующих разделах рассматриваются эти действия и представляется краткое введение в следующие вопросы.  
  
- обработка ошибок;  
  
- Настройка и обеспечение безопасности клиентов.  
  
- Создание объектов обратного вызова для дуплексных служб.  
  
- Вызов служб асинхронно.  
  
- Вызов служб с использованием клиентских каналов.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Получение контракта службы, привязок и адресов  
 В WCF службы и клиенты моделируют контракты с использованием управляемых атрибутов, интерфейсов и методов. Чтобы подключиться к службе в клиентском приложении, необходимо получить информацию о типе для контракта службы. Как правило, вы делаете это с помощью [инструмента ServiceModel Metadata Utility Tool (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md)который загружает метаданные из службы, преобразует их в управляемый файл исходного кода на языке по вашему выбору и создает файл конфигурации клиентского приложения, который можно использовать для настройки вашего объекта клиента WCF. Например, если вы собираетесь создать объект клиента WCF `MyCalculatorService`для вызывать a, и вы знаете, `http://computerName/MyCalculatorService/Service.svc?wsdl`что метаданные для этой службы публикуются на, то `ClientCode.vb` следующий пример кода показывает, как использовать Svcutil.exe для получения файла, содержащего контракт службы в управляемом коде.  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Этот код контракта можно компилировать либо в клиентское приложение, либо в другую сборку, которую клиентское приложение может затем использовать для создания объекта клиента WCF. Можно использовать файл конфигурации, чтобы настроить объект клиента для правильного подключения к службе.  
  
 Например, в этом процессе см., [как: Создать клиента](how-to-create-a-wcf-client.md). Для получения более полной информации о контрактах [см.](./feature-details/contracts.md)  
  
## <a name="create-a-wcf-client-object"></a>Создание объекта клиента WCF  
 Клиент WCF — это локальный объект, представляющий службу WCF в форме, которую клиент может использовать для связи с удаленной службой. Типы клиентов WCF реализуют целевой контракт службы, поэтому при его создании и настройке можно использовать объект клиента непосредственно для вызывать операции службы. Время выполнения WCF преобразует вызовы метода в сообщения, отправляет их в службу, выслушивает ответ и возвращает эти `out` значения `ref` объекту клиента WCF в качестве значений возврата или параметров.  
  
 Вы также можете использовать объекты клиентского канала WCF для подключения и использования служб. Для получения подробной информации [см.](./feature-details/client-architecture.md)  
  
#### <a name="creating-a-new-wcf-object"></a>Создание нового объекта WCF  
 Чтобы продемонстрировать использование класса <xref:System.ServiceModel.ClientBase%601>, предположим, что следующий простой контракт службы создан из приложения службы.  
  
> [!NOTE]
> Если вы используете Visual Studio для создания клиента WCF, объекты автоматически загружаются в браузер объекта при добавлении ссылки на проект.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Если вы не используете Visual Studio, изучите сгенерированный код контракта, чтобы найти тип, который <xref:System.ServiceModel.ClientBase%601> расширяется, и интерфейс `ISampleService`контракта на обслуживание. В этом случае такой тип выглядит как следующий код.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Этот класс можно создать как локальный объект с использованием одного из конструкторов, который настроен и используется для подключения к службе, принадлежащей к типу `ISampleService`.  
  
 Рекомендуется сначала создать клиентский объект WCF, а затем использовать его и закрыть его в одном блоке try/catch. Не следует использовать `using` выписку (в`Using` Visual Basic), поскольку она может маскировать исключения в определенных режимах сбоя. Для получения дополнительной информации смотрите следующие разделы, а также [использовать close и Abort для выпуска ресурсов клиентов WCF.](./samples/use-close-abort-release-wcf-client-resources.md)  
  
### <a name="contracts-bindings-and-addresses"></a>Контракты, привязки и адреса  
 Прежде чем создать клиентский объект WCF необходимо настроить объект клиента. В частности, он должен иметь *конечную точку* службы для использования. Конечная точка - это комбинация контракта службы, привязки и адреса. (Для получения дополнительной информации [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md)о конечных точках см. Как правило, эта информация находится в [ \<конечных>](../configure-apps/file-schema/wcf/endpoint-of-client.md) элементе в файле конфигурации клиентского приложения, например, инструментs Svcutil.exe, и загружается автоматически при создании объекта клиента. Оба типа клиентов WCF также имеют перегрузки, которые позволяют программно указать эту информацию.  
  
 Например, созданный файл конфигурации для службы `ISampleService`, используемый в предыдущих примерах, содержит следующие сведения о конечных точках.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Этот файл конфигурации содержит целевую конечную точку в элементе `<client>`. Для получения дополнительной информации об использовании <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> нескольких целевых конечных точек см. <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType>  
  
## <a name="calling-operations"></a>Вызов операций  
 Если у вас создан и настроен объект клиента, создайте блок try/catch, вызов операций таким же образом, как если бы объект был локальным, и закройте объект клиента WCF. Когда клиентское приложение вызывает первую операцию, WCF автоматически открывает основной канал, и основной канал закрывается при переработке объекта. (Также можно явно открыть и закрыть канал до или после вызова других операций.)  
  
 Например, в случае следующего контракта службы.  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _
   Public Interface ICalculator  
        <OperationContract> _
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 Операции можно вызвать, создав клиентский объект WCF и назвав его методы, как показано на примере следующего кода. Обратите внимание, что открытие, вызов и закрытие объекта клиента WCF происходит в пределах одного блока try/catch. Для получения дополнительной [информации см. Услуги доступа с помощью клиента WCF](./feature-details/accessing-services-using-a-client.md) и [использование close and Abort для выпуска клиентских ресурсов WCF.](./samples/use-close-abort-release-wcf-client-resources.md)  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Обработка ошибок  
 Исключения могут возникать в клиентском приложении при открытии базового клиентского канала (как явно, так и автоматически путем вызова операции) с использованием клиента или объекта канала для вызова операций или при закрытии базового клиентского канала. Рекомендуется, чтобы приложения по крайней мере обрабатывали возможные исключения <xref:System.TimeoutException?displayProperty=nameWithType> и <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> помимо любых объектов <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, созданных в результате ошибок SOAP, возвращенных операциями. Ошибки протокола SOAP, указанные в контракте операции, распространяются до клиентских приложений в виде исключения <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, в котором параметр типа представляет собой тип сведений ошибки SOAP. Для получения дополнительной информации об условиях обработки ошибок в клиентском приложении [см.](sending-and-receiving-faults.md) Для полного образца показано, как обрабатывать ошибки в клиенте, [см.](./samples/expected-exceptions.md)  
  
## <a name="configuring-and-securing-clients"></a>Настройка и обеспечение безопасности клиентов  
 Настройка клиента начинается с обязательной загрузки информации о целевых конечных точках для клиента или объекта канала, как правило, из файла конфигурации, хотя эту информацию также можно загрузить программными средствами с использованием конструкторов и свойств клиента. Однако для включения определенного поведения клиента и для большинства сценариев безопасности требуются дополнительные этапы конфигурации.  
  
 Например, требования безопасности для контрактов службы объявлены в интерфейсе контрактов службы, и если Svcutil.exe создал файл конфигурации, этот файл обычно содержит привязку, которая может поддерживать требования безопасности службы. Однако в некоторых случаях может потребоваться более точная конфигурация безопасности, например настройка учетных данных клиента. Для получения полной информации о конфигурации безопасности для клиентов WCF, [см.](securing-clients.md)  
  
 Кроме того, можно включить некоторые пользовательские изменения в клиентские приложения, такие как пользовательское поведение во время выполнения. Для получения дополнительной информации о том, как настроить пользовательское поведение клиента, [см.](configuring-client-behaviors.md)  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Создание объектов обратного вызова для дуплексных служб  
 Дуплексные службы задают контракт обратного вызова, который должно реализовать клиентское приложение, чтобы обеспечить объект обратного вызова для вызываемой службы в соответствии с требованиями контракта. Хотя объекты обратного вызова не являются полноценными службами (например, невозможно инициировать канал с объектом обратного вызова), в целях реализации и конфигурации их можно рассматривать как тип службы.  
  
 Клиенты дуплексных служб должны выполнять следующее.  
  
- Реализовывать класс контракта обратного вызова.  
  
- Создайте экземпляр класса реализации договора обратного вызова <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> и используйте его для создания объекта, который вы передаем к конструктору клиента WCF.  
  
- Вызывать операции и обрабатывать обратные вызовы операций.  
  
 Клиентские объекты Duplex WCF функционируют как их аналоги nonduplex, за исключением того, что они предоставляют функциональность, необходимую для поддержки обратных вызовов, включая конфигурацию службы обратного вызова.  
  
 Например, невозможно управлять различными аспектами поведения среды выполнения объекта обратного вызова, используя свойства атрибута <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> класса обратного вызова. Еще одним примером является использование класса <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> для включения возвращения сведений об исключениях в службы, вызывающие объект обратного вызова. Для получения дополнительной информации [см.](./feature-details/duplex-services.md) Для полного образца [см.](./samples/duplex.md)  
  
 На компьютерах под управлением ОС Windows XP с запущенными службами IIS 5.1 дуплексные клиенты должны задавать базовый адрес клиента с помощью класса <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, в противном случае возникает исключение. В следующем примере кода показано, как это сделать в коде.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 В следующем коде показано, как это сделать в файле конфигурации.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Вызов служб асинхронно  
 Способ вызова операций полностью зависит от разработчика клиента. Это объясняется тем, что сообщения, составляющие операцию, можно сопоставить синхронному или асинхронному методу с использованием управляемого кода. Следовательно, если необходимо создать клиент, который вызывает операции асинхронно, можно использовать Svcutil.exe для создания асинхронного кода клиента с помощью параметра `/async`. Для получения дополнительной информации, [см. Как: Вызов службы операций Асинхронно](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Вызов служб с использованием клиентских каналов WCF  
 Типы клиентов <xref:System.ServiceModel.ClientBase%601>WCF расширяются, что само по себе вытекает из <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> интерфейса, чтобы разоблачить базовую систему каналов. Можно вызвать службы с помощью целевого контракта службы с классом <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Для получения подробной информации [см.](./feature-details/client-architecture.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
