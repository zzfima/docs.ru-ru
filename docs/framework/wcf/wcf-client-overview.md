---
title: Общие сведения о клиентах WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 1aa540d084e9b11cc7a355db02047705f55ea4be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-client-overview"></a>Общие сведения о клиентах WCF
В этом разделе описываются выполните клиентских приложений, способы настройки, создания и использования клиента Windows Communication Foundation (WCF) и обеспечении безопасности клиентских приложений.  
  
## <a name="using-wcf-client-objects"></a>Использование объектов клиента WCF  
 Клиентское приложение представляет собой управляемое приложение, использующее клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для взаимодействия с другим приложением. Чтобы создать клиентское приложение для службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], необходимо выполнить следующее.  
  
1.  Получите контракт службы, привязки и адрес для конечной точки службы.  
  
2.  Создайте клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], используя эту информацию.  
  
3.  Вызовите операции.  
  
4.  Закройте объект клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 В последующих разделах рассматриваются эти действия и представляется краткое введение в следующие вопросы.  
  
-   Обработка ошибок.  
  
-   Настройка и обеспечение безопасности клиентов.  
  
-   Создание объектов обратного вызова для дуплексных служб.  
  
-   Вызов служб асинхронно.  
  
-   Вызов служб с использованием клиентских каналов.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Получение контракта службы, привязок и адресов  
 В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службы и клиенты моделируют контракты с использованием управляемых атрибутов, интерфейсов и методов. Чтобы подключиться к службе в клиентском приложении, необходимо получить информацию о типе для контракта службы. Как правило, это делается с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), который загружает метаданные из службы, преобразует его в файл управляемого исходного кода на языке и создает клиент файл конфигурации приложения, который можно использовать для настройки вашей [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] клиентский объект. Например, если необходимо создать объект клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], чтобы вызвать службу `MyCalculatorService`, и известно, что метаданные для этой службы опубликованы по адресу `http://computerName/MyCalculatorService/Service.svc?wsdl`, в следующем примере кода показано, как использовать Svcutil.exe, чтобы получить файл `ClientCode.vb`, содержащий контракт службы в управляемом коде.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 Можно компилировать этот код контракта либо в клиентское приложение, либо в другую сборку, которую может использовать клиентское приложение для создания объекта клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Можно использовать файл конфигурации, чтобы настроить объект клиента для правильного подключения к службе.  
  
 Пример этого процесса см. в разделе [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Более полные сведения о контрактах см. в разделе [контракты](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Создание объекта клиента WCF  
 Клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] - это локальный объект, представляющий службу [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в форме, которую клиент может использовать для взаимодействия с удаленной службой. Тип клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] реализует целевой контракт службы, поэтому при создании и настройке объекта клиента вы можете непосредственно использовать его для вызова операций службы. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Запуска преобразует время, метод вызывает в сообщения, отправляемый службе, ожидает ответа и возвращает эти значения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] клиентского объекта в качестве возвращаемых значений или `out` или `ref` параметров.  
  
 Также можно использовать объекты клиентских каналов [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для подключения к службам и их использования. Дополнительные сведения см. в разделе [Клиентская архитектура технологии WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Создание нового объекта WCF  
 Чтобы продемонстрировать использование класса <xref:System.ServiceModel.ClientBase%601>, предположим, что следующий простой контракт службы создан из приложения службы.  
  
> [!NOTE]
>  Если вы используете Visual Studio для создания вашего [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] клиента, объекты загружаются автоматически в браузер объектов при добавлении ссылки на службу в проект.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Если вы не используете Visual Studio, проверьте созданный код контракта и найдите тип, расширяющий <xref:System.ServiceModel.ClientBase%601> и интерфейс контракта службы `ISampleService`. В этом случае такой тип выглядит как следующий код.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Этот класс можно создать как локальный объект с использованием одного из конструкторов, который настроен и используется для подключения к службе, принадлежащей к типу `ISampleService`.  
  
 Рекомендуется сначала создать объект клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], затем использовать и закрыть его внутри одного блока try/catch. Не следует использовать `using` инструкции (`Using` в Visual Basic), так как она может маскировать исключения в некоторых режимах сбоя. Дополнительные сведения см. в следующих разделах в том числе в [как избежать проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Контракты, привязки и адреса  
 Перед созданием объекта клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] его необходимо настроить. В частности, он должен иметь службы *конечная точка* для использования. Конечная точка - это комбинация контракта службы, привязки и адреса. (Дополнительные сведения о конечных точках см. в разделе [конечные точки: адреса, привязки и контракты](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) Как правило, эта информация содержится в [ \<endpoint >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) элемент в файле конфигурации приложения клиента, такие как средство Svcutil.exe, приводит к возникновению ошибки, и загружается автоматически при создании клиента объект. Оба типа клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] также имеют перегрузки, которые позволяют указывать эту информацию программными средствами.  
  
 Например, созданный файл конфигурации для службы `ISampleService`, используемый в предыдущих примерах, содержит следующие сведения о конечных точках.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Этот файл конфигурации содержит целевую конечную точку в элементе `<client>`. Дополнительные сведения об использовании нескольких целевых конечных точек см. в разделе <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> конструкторы.  
  
## <a name="calling-operations"></a>Вызов операций  
 После создания и настройки объекта клиента создайте блок try/catch, вызовите операции таким же способом, как если бы объект был локальным, и закройте объект клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Когда клиентское приложение вызывает первую операцию, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] автоматически открывает базовый канал, который закрывается после утилизации объекта. (Также можно явно открыть и закрыть канал до или после вызова других операций.)  
  
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
  
 Можно вызвать операции, создав объект клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и вызвав его методы, как показано в следующим примере кода. Обратите внимание, что открытие, вызов и закрытие объекта клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] выполняется в пределах одного блока try/catch. Дополнительные сведения см. в разделе [получение служб с помощью клиента WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) и [как избежать проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Обработка ошибок  
 Исключения могут возникать в клиентском приложении при открытии базового клиентского канала (как явно, так и автоматически путем вызова операции) с использованием клиента или объекта канала для вызова операций или при закрытии базового клиентского канала. Рекомендуется, чтобы приложения по крайней мере обрабатывали возможные исключения <xref:System.TimeoutException?displayProperty=nameWithType> и <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> помимо любых объектов <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, созданных в результате ошибок SOAP, возвращенных операциями. Ошибки протокола SOAP, указанные в контракте операции, распространяются до клиентских приложений в виде исключения <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>, в котором параметр типа представляет собой тип сведений ошибки SOAP. Дополнительные сведения об обработке ошибок в клиентском приложении см. в разделе [отправка и получение ошибки](../../../docs/framework/wcf/sending-and-receiving-faults.md). Полный пример процедуры для обработки ошибок в клиенте, см. в разделе [ожидаемого исключения](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Настройка и обеспечение безопасности клиентов  
 Настройка клиента начинается с обязательной загрузки информации о целевых конечных точках для клиента или объекта канала, как правило, из файла конфигурации, хотя эту информацию также можно загрузить программными средствами с использованием конструкторов и свойств клиента. Однако для включения определенного поведения клиента и для большинства сценариев безопасности требуются дополнительные этапы конфигурации.  
  
 Например, требования безопасности для контрактов службы объявлены в интерфейсе контрактов службы, и если Svcutil.exe создал файл конфигурации, этот файл обычно содержит привязку, которая может поддерживать требования безопасности службы. Однако в некоторых случаях может потребоваться более точная конфигурация безопасности, например настройка учетных данных клиента. Дополнительные сведения о конфигурации безопасности для [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] клиентов, в разделе [обеспечение безопасности клиентов](../../../docs/framework/wcf/securing-clients.md).  
  
 Кроме того, можно включить некоторые пользовательские изменения в клиентские приложения, такие как пользовательское поведение во время выполнения. Дополнительные сведения о способах настройки пользовательского поведения клиента см. в разделе [Настройка поведений клиента](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Создание объектов обратного вызова для дуплексных служб  
 Дуплексные службы задают контракт обратного вызова, который должно реализовать клиентское приложение, чтобы обеспечить объект обратного вызова для вызываемой службы в соответствии с требованиями контракта. Хотя объекты обратного вызова не являются полноценными службами (например, невозможно инициировать канал с объектом обратного вызова), в целях реализации и конфигурации их можно рассматривать как тип службы.  
  
 Клиенты дуплексных служб должны выполнять следующее.  
  
-   Реализовывать класс контракта обратного вызова.  
  
-   Создавать экземпляр класса реализации контракта обратного вызова и использовать его для создания объекта <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>, передаваемого в конструктор клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Вызывать операции и обрабатывать обратные вызовы операций.  
  
 Дуплексные объекты клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] функционируют как их недуплексные аналоги, за исключением того, что они предоставляют функциональные возможности, необходимые для поддержки обратных вызовов, включая конфигурацию службы обратного вызова.  
  
 Например, невозможно управлять различными аспектами поведения среды выполнения объекта обратного вызова, используя свойства атрибута <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> класса обратного вызова. Еще одним примером является использование класса <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> для включения возвращения сведений об исключениях в службы, вызывающие объект обратного вызова. Дополнительные сведения см. в разделе [дуплексные службы](../../../docs/framework/wcf/feature-details/duplex-services.md). Полный пример см. в разделе [дуплексного](../../../docs/framework/wcf/samples/duplex.md).  
  
 На компьютерах под управлением ОС Windows XP с запущенными службами IIS 5.1 дуплексные клиенты должны задавать базовый адрес клиента с помощью класса <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, в противном случае возникает исключение. В следующем примере кода показано, как это сделать в коде.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 В следующем коде показано, как это сделать в файле конфигурации.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Вызов служб асинхронно  
 Способ вызова операций полностью зависит от разработчика клиента. Это объясняется тем, что сообщения, составляющие операцию, можно сопоставить синхронному или асинхронному методу с использованием управляемого кода. Следовательно, если необходимо создать клиент, который вызывает операции асинхронно, можно использовать Svcutil.exe для создания асинхронного кода клиента с помощью параметра `/async`. Дополнительные сведения см. в разделе [как: асинхронно вызывать операции службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Вызов служб с использованием клиентских каналов WCF  
 Типы клиентов [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] расширяют класс <xref:System.ServiceModel.ClientBase%601>, который наследуется от интерфейса <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, чтобы предоставить систему базовых каналов. Можно вызвать службы с помощью целевого контракта службы с классом <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Клиентская архитектура технологии WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
