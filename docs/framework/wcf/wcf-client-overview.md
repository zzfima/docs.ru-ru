---
title: Общие сведения о клиентах WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: e6e7d9fe6764120e3d676b9d2cbd248e7491e504
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152634"
---
# <a name="wcf-client-overview"></a>Общие сведения о клиентах WCF
В этом разделе описывается, выполняемые клиентским приложениям, как настроить, создать и использовать клиент Windows Communication Foundation (WCF) и как защитить клиентские приложения.  
  
## <a name="using-wcf-client-objects"></a>Использование объектов клиента WCF  
 Клиентское приложение представляет собой управляемое приложение, который клиент WCF для взаимодействия с другим приложением. Создание клиента приложения для службы WCF необходимо выполнить следующие действия:  
  
1.  Получите контракт службы, привязки и адрес для конечной точки службы.  
  
2.  Создание клиента WCF с помощью этой информации.  
  
3.  Вызовите операции.  
  
4.  Закройте объект клиента WCF.  
  
 В последующих разделах рассматриваются эти действия и представляется краткое введение в следующие вопросы.  
  
-   Обработка ошибок.  
  
-   Настройка и обеспечение безопасности клиентов.  
  
-   Создание объектов обратного вызова для дуплексных служб.  
  
-   Вызов служб асинхронно.  
  
-   Вызов служб с использованием клиентских каналов.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Получение контракта службы, привязок и адресов  
 В WCF службы и клиенты моделируют контракты с использованием управляемых атрибутов, интерфейсов и методов. Чтобы подключиться к службе в клиентском приложении, необходимо получить информацию о типе для контракта службы. Как правило, это сделать с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), который загружает метаданные из службы, преобразует его в файл управляемого исходного кода на языке по вашему выбору и создает клиент файл конфигурации приложения, который можно использовать для настройки объекта клиента WCF. Например, если вы собираетесь создать объекта клиента WCF для вызова `MyCalculatorService`, и вы знаете, что метаданные для этой службы публикуются в `http://computerName/MyCalculatorService/Service.svc?wsdl`, а затем в следующем примере кода показано, как использовать Svcutil.exe для получения `ClientCode.vb` файла, который содержащий контракт службы в управляемом коде.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Либо можно скомпилировать этот код контракта в клиентское приложение или в другую сборку, клиентское приложение затем можно использовать для создания объекта клиента WCF. Можно использовать файл конфигурации, чтобы настроить объект клиента для правильного подключения к службе.  
  
 Пример того, этот процесс, см. в разделе [как: Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Более полные сведения о контрактах см. в разделе [контракты](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Создание объекта клиента WCF  
 Клиент WCF — это локальный объект, представляющий службу WCF в форме, которую клиент может использовать для взаимодействия с удаленной службой. Типы клиентов WCF реализовать целевой службы контрактов, поэтому, если создать и настроить его, затем можно использовать объект клиента непосредственно для вызова операций службы. Среда выполнения WCF преобразует эти вызовы методов в сообщения, отправляет их в службу, ожидает ответа и возвращает эти значения для объекта клиента WCF в качестве возвращаемых значений или `out` или `ref` параметров.  
  
 Можно также использовать объекты клиентских каналов WCF подключать и использовать службы. Дополнительные сведения см. в разделе [Клиентская архитектура технологии WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Создание нового объекта WCF  
 Чтобы продемонстрировать использование класса <xref:System.ServiceModel.ClientBase%601>, предположим, что следующий простой контракт службы создан из приложения службы.  
  
> [!NOTE]
>  Если вы используете Visual Studio для создания клиента WCF, объекты загружаются автоматически в обозревателе объектов при добавлении ссылки на службу в проект.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Если вы не используете Visual Studio, изучите создаваемого кода контракта для поиска типа, который расширяет <xref:System.ServiceModel.ClientBase%601> и интерфейс контракта службы `ISampleService`. В этом случае такой тип выглядит как следующий код.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Этот класс можно создать как локальный объект с использованием одного из конструкторов, который настроен и используется для подключения к службе, принадлежащей к типу `ISampleService`.  
  
 Рекомендуется сначала создать объекта клиента WCF и затем использовать его и закрыть его внутри одного блока try/catch блока. Не следует использовать `using` инструкции (`Using` в Visual Basic), так как она может маскировать исключения в определенных режимах сбоя. Дополнительные сведения см. в разделах также [используйте Close и Abort для освобождения ресурсов клиента WCF](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Контракты, привязки и адреса  
 Перед созданием объекта клиента WCF, необходимо настроить объект клиента. В частности, должны иметь службу *конечной точки* для использования. Конечная точка - это комбинация контракта службы, привязки и адреса. (Дополнительные сведения о конечных точках см. в разделе [конечные точки: Адреса, привязки и контракты](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) Как правило, эта информация находится в [ \<конечной точки >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) элемент в файле конфигурации клиентского приложения, например в каталог, средство Svcutil.exe создает и загружается автоматически при создании клиента объект. Оба типа клиента WCF также имеют перегрузки, дающие возможность программно указать эти сведения.  
  
 Например, созданный файл конфигурации для службы `ISampleService`, используемый в предыдущих примерах, содержит следующие сведения о конечных точках.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Этот файл конфигурации содержит целевую конечную точку в элементе `<client>`. Дополнительные сведения об использовании нескольких целевых конечных точек см. в разделе <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> конструкторы.  
  
## <a name="calling-operations"></a>Вызов операций  
 После создания объекта клиента и настроен, создайте блок try/catch, вызовите операции таким же образом, если эти объекты были локальными бы и закрытие объекта клиента WCF. Когда клиентское приложение вызывает первую операцию, WCF автоматически открывает базовый канал и закрывается при перезапуске объекта. (Также можно явно открыть и закрыть канал до или после вызова других операций.)  
  
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
  
 Операции можно вызвать путем создания объекта клиента WCF и вызова его методов, как в следующем примере кода демонстрируется. Обратите внимание на то, что открытие, вызов и закрытие объекта клиента WCF происходит в пределах одного блока try/catch блока. Дополнительные сведения см. в разделе [доступ к службам, с помощью клиента WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) и [используйте Close и Abort для освобождения ресурсов клиента WCF](../../../docs/framework/wcf/samples/use-close-abort-release-wcf-client-resources.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Обработка ошибок  
 Исключения могут возникать в клиентском приложении при открытии базового клиентского канала (как явно, так и автоматически путем вызова операции) с использованием клиента или объекта канала для вызова операций или при закрытии базового клиентского канала. Рекомендуется, чтобы приложения по крайней мере обрабатывали возможные исключения <xref:System.TimeoutException?displayProperty=nameWithType> и <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> помимо любых объектов <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, созданных в результате ошибок SOAP, возвращенных операциями. Ошибки протокола SOAP, указанные в контракте операции, распространяются до клиентских приложений в виде исключения <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, в котором параметр типа представляет собой тип сведений ошибки SOAP. Дополнительные сведения об обработке ошибок в клиентском приложении см. в разделе [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md). Полный пример процедуры обработки ошибок в клиенте, см. в разделе [ожидается исключения](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Настройка и обеспечение безопасности клиентов  
 Настройка клиента начинается с обязательной загрузки информации о целевых конечных точках для клиента или объекта канала, как правило, из файла конфигурации, хотя эту информацию также можно загрузить программными средствами с использованием конструкторов и свойств клиента. Однако для включения определенного поведения клиента и для большинства сценариев безопасности требуются дополнительные этапы конфигурации.  
  
 Например, требования безопасности для контрактов службы объявлены в интерфейсе контрактов службы, и если Svcutil.exe создал файл конфигурации, этот файл обычно содержит привязку, которая может поддерживать требования безопасности службы. Однако в некоторых случаях может потребоваться более точная конфигурация безопасности, например настройка учетных данных клиента. Полные сведения о конфигурации безопасности для клиентов WCF см. в разделе [обеспечение безопасности клиентов](../../../docs/framework/wcf/securing-clients.md).  
  
 Кроме того, можно включить некоторые пользовательские изменения в клиентские приложения, такие как пользовательское поведение во время выполнения. Дополнительные сведения о способах настройки пользовательского поведения клиента см. в разделе [Настройка поведений клиента](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Создание объектов обратного вызова для дуплексных служб  
 Дуплексные службы задают контракт обратного вызова, который должно реализовать клиентское приложение, чтобы обеспечить объект обратного вызова для вызываемой службы в соответствии с требованиями контракта. Хотя объекты обратного вызова не являются полноценными службами (например, невозможно инициировать канал с объектом обратного вызова), в целях реализации и конфигурации их можно рассматривать как тип службы.  
  
 Клиенты дуплексных служб должны выполнять следующее.  
  
-   Реализовывать класс контракта обратного вызова.  
  
-   Создайте экземпляр класса реализации контракта обратного вызова и использовать его для создания <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> объект, передаваемый в конструктор клиента WCF.  
  
-   Вызывать операции и обрабатывать обратные вызовы операций.  
  
 Дуплекс объектов клиента WCF, такие как их недуплексные аналоги, за исключением, что они предоставляют функциональные возможности, необходимые для поддержки обратных вызовов, включая конфигурацию службы обратного вызова.  
  
 Например, невозможно управлять различными аспектами поведения среды выполнения объекта обратного вызова, используя свойства атрибута <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> класса обратного вызова. Еще одним примером является использование класса <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> для включения возвращения сведений об исключениях в службы, вызывающие объект обратного вызова. Дополнительные сведения см. в разделе [дуплексные службы](../../../docs/framework/wcf/feature-details/duplex-services.md). Полный пример см. в разделе [дуплексного](../../../docs/framework/wcf/samples/duplex.md).  
  
 На компьютерах под управлением ОС Windows XP с запущенными службами IIS 5.1 дуплексные клиенты должны задавать базовый адрес клиента с помощью класса <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, в противном случае возникает исключение. В следующем примере кода показано, как это сделать в коде.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 В следующем коде показано, как это сделать в файле конфигурации.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Вызов служб асинхронно  
 Способ вызова операций полностью зависит от разработчика клиента. Это объясняется тем, что сообщения, составляющие операцию, можно сопоставить синхронному или асинхронному методу с использованием управляемого кода. Следовательно, если необходимо создать клиент, который вызывает операции асинхронно, можно использовать Svcutil.exe для создания асинхронного кода клиента с помощью параметра `/async`. Дополнительные сведения см. в разделе [Как Асинхронный вызов операций службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Вызов служб с использованием клиентских каналов WCF  
 Расширения типов клиентов WCF <xref:System.ServiceModel.ClientBase%601>, который сам является производным от <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> интерфейс, предоставляемый системой базовых каналов. Можно вызвать службы с помощью целевого контракта службы с классом <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Клиентская архитектура технологии WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
