---
title: 'Пользовательский кодировщик сообщений: Пользовательский кодировщик текстовых - WCF'
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 8cbdb9e2a17eb006b589fe42fe6adf62ce37d340
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878398"
---
# <a name="custom-message-encoder-custom-text-encoder"></a><span data-ttu-id="1f66c-102">Пользовательский кодировщик сообщений: пользовательский кодировщик текста</span><span class="sxs-lookup"><span data-stu-id="1f66c-102">Custom Message Encoder: Custom Text Encoder</span></span>

<span data-ttu-id="1f66c-103">В этом примере показано, как реализовать пользовательский кодировщик текстовых сообщений с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1f66c-103">This sample demonstrates how to implement a custom text message encoder using Windows Communication Foundation (WCF).</span></span>

> [!WARNING]
> <span data-ttu-id="1f66c-104">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1f66c-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1f66c-105">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1f66c-105">Check for the following (default) directory before continuing.</span></span>
> 
> `<InstallDrive>:\WF_WCF_Samples`
> 
> <span data-ttu-id="1f66c-106">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="1f66c-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1f66c-107">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="1f66c-107">This sample is located in the following directory.</span></span>
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

<span data-ttu-id="1f66c-108"><xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> Из WCF поддерживает только кодировки Юникод UTF-8 и UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="1f66c-108">The <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF supports only the UTF-8, UTF-16 and big-endian Unicode encodings.</span></span> <span data-ttu-id="1f66c-109">Пользовательский кодировщик текстовых сообщений в этом образце поддерживает все поддерживаемые платформы кодировок, которые могут потребоваться для совместимости.</span><span class="sxs-lookup"><span data-stu-id="1f66c-109">The custom text message encoder in this sample supports all platform-supported character encodings that may be required for interoperability.</span></span> <span data-ttu-id="1f66c-110">Образец состоит из консольной программы клиента (.exe), библиотеку службы (DLL-файл), размещаемую Internet Information Services (IIS) и библиотеку кодировщика сообщений текст (.dll).</span><span class="sxs-lookup"><span data-stu-id="1f66c-110">The sample consists of a client console program (.exe), a service library (.dll) hosted by Internet Information Services (IIS), and a text message encoder library (.dll).</span></span> <span data-ttu-id="1f66c-111">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="1f66c-111">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="1f66c-112">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (добавить, вычесть, умножить и разделить).</span><span class="sxs-lookup"><span data-stu-id="1f66c-112">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="1f66c-113">Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="1f66c-113">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="1f66c-114">Как клиент, так и служба используют кодировщик `CustomTextMessageEncoder` вместо кодировщика по умолчанию <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1f66c-114">Both client and service uses the `CustomTextMessageEncoder` instead of the default <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span>

<span data-ttu-id="1f66c-115">Реализация пользовательского кодировщика состоит из фабрики кодировщиков сообщений, кодировщика сообщений, элемента привязки кодировщика сообщений и обработчика конфигурации. При этом демонстрируются следующие операции.</span><span class="sxs-lookup"><span data-stu-id="1f66c-115">The custom encoder implementation consists of a message encoder factory, a message encoder, a message encoding binding element and a configuration handler, and demonstrates the following:</span></span>

- <span data-ttu-id="1f66c-116">Построение пользовательского кодировщика и фабрики кодировщика.</span><span class="sxs-lookup"><span data-stu-id="1f66c-116">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="1f66c-117">Создание элемента привязки для пользовательского кодировщика.</span><span class="sxs-lookup"><span data-stu-id="1f66c-117">Creating a binding element for a custom encoder.</span></span>

- <span data-ttu-id="1f66c-118">Использование конфигурации пользовательской привязки для интеграции элементов пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="1f66c-118">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="1f66c-119">Разработка обработчика пользовательской конфигурации для обеспечения настройки элемента пользовательской привязки в файле.</span><span class="sxs-lookup"><span data-stu-id="1f66c-119">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1f66c-120">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="1f66c-120">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1f66c-121">Установка ASP.NET 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1f66c-121">Install ASP.NET 4.0 using the following command.</span></span>

    ```
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="1f66c-122">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f66c-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="1f66c-123">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f66c-123">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="1f66c-124">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f66c-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="message-encoder-factory-and-the-message-encoder"></a><span data-ttu-id="1f66c-125">Фабрика кодировщика сообщений и кодировщик сообщений</span><span class="sxs-lookup"><span data-stu-id="1f66c-125">Message Encoder Factory and the Message Encoder</span></span>

<span data-ttu-id="1f66c-126">При открытии <xref:System.ServiceModel.ServiceHost> или канала клиента компонент времени разработки `CustomTextMessageBindingElement` создает фабрику `CustomTextMessageEncoderFactory`.</span><span class="sxs-lookup"><span data-stu-id="1f66c-126">When the <xref:System.ServiceModel.ServiceHost> or the client channel is opened, the design time component `CustomTextMessageBindingElement` creates the `CustomTextMessageEncoderFactory`.</span></span> <span data-ttu-id="1f66c-127">Фабрика создает кодировщик `CustomTextMessageEncoder`.</span><span class="sxs-lookup"><span data-stu-id="1f66c-127">The factory creates the `CustomTextMessageEncoder`.</span></span> <span data-ttu-id="1f66c-128">Кодировщик сообщений работает как в режиме буферизации, так и в режиме потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="1f66c-128">The message encoder operates both in the streaming mode and the buffered mode.</span></span> <span data-ttu-id="1f66c-129">Он использует классы <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter> для чтения и записи сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="1f66c-129">It uses the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to read and write the messages respectively.</span></span> <span data-ttu-id="1f66c-130">В отличие от оптимизированных средств чтения XML и записи WCF, которые поддерживает только UTF-8 UTF-16 и big endian Unicode, эти средства чтения и записи поддерживают все поддерживаемые платформы кодирование.</span><span class="sxs-lookup"><span data-stu-id="1f66c-130">As opposed to the optimized XML readers and writers of WCF that support only UTF-8, UTF-16 and big-endian Unicode, these readers and writers support all platform-supported encoding.</span></span>

<span data-ttu-id="1f66c-131">В следующем примере кода показан кодировщик CustomTextMessageEncoder.</span><span class="sxs-lookup"><span data-stu-id="1f66c-131">The following code example shows the CustomTextMessageEncoder.</span></span>

```csharp
public class CustomTextMessageEncoder : MessageEncoder
{
    private CustomTextMessageEncoderFactory factory;
    private XmlWriterSettings writerSettings;
    private string contentType;

    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)
    {
        this.factory = factory;

        this.writerSettings = new XmlWriterSettings();
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);
        this.contentType = $"{this.factory.MediaType}; charset={this.writerSettings.Encoding.HeaderName}";
    }

    public override string ContentType
    {
        get
        {
            return this.contentType;
        }
    }

    public override string MediaType
    {
        get 
        {
            return factory.MediaType;
        }
    }

    public override MessageVersion MessageVersion
    {
        get 
        {
            return this.factory.MessageVersion;
        }
    }

    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)
    {   
        byte[] msgContents = new byte[buffer.Count];
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);
        bufferManager.ReturnBuffer(buffer.Array);

        MemoryStream stream = new MemoryStream(msgContents);
        return ReadMessage(stream, int.MaxValue);
    }

    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)
    {
        XmlReader reader = XmlReader.Create(stream);
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);
    }

    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)
    {
        MemoryStream stream = new MemoryStream();
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();

        byte[] messageBytes = stream.GetBuffer();
        int messageLength = (int)stream.Position;
        stream.Close();

        int totalLength = messageLength + messageOffset;
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);

        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);
        return byteArray;
    }

    public override void WriteMessage(Message message, Stream stream)
    {
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();
    }
}
```

<span data-ttu-id="1f66c-132">В следующем примере кода показано, как построить фабрику кодировщиков сообщений.</span><span class="sxs-lookup"><span data-stu-id="1f66c-132">The following code example shows how to build the message encoder factory.</span></span>

```csharp
public class CustomTextMessageEncoderFactory : MessageEncoderFactory
{
    private MessageEncoder encoder;
    private MessageVersion version;
    private string mediaType;
    private string charSet;

    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,
        MessageVersion version)
    {
        this.version = version;
        this.mediaType = mediaType;
        this.charSet = charSet;
        this.encoder = new CustomTextMessageEncoder(this);
    }

    public override MessageEncoder Encoder
    {
        get 
        { 
            return this.encoder;
        }
    }

    public override MessageVersion MessageVersion
    {
        get 
        { 
            return this.version;
        }
    }

    internal string MediaType
    {
        get
        {
            return this.mediaType;
        }
    }

    internal string CharSet
    {
        get
        {
            return this.charSet;
        }
    }
}
```

## <a name="message-encoding-binding-element"></a><span data-ttu-id="1f66c-133">Элемент привязки кодирования сообщений</span><span class="sxs-lookup"><span data-stu-id="1f66c-133">Message Encoding Binding Element</span></span>

<span data-ttu-id="1f66c-134">Элементы привязки обеспечивают настройку стека времени выполнения WCF.</span><span class="sxs-lookup"><span data-stu-id="1f66c-134">The binding elements allow the configuration of the WCF run-time stack.</span></span> <span data-ttu-id="1f66c-135">Чтобы использовать пользовательский кодировщик сообщений в приложении WCF, необходим элемент привязки, создающий фабрику кодировщиков сообщений с соответствующими параметрами на соответствующем уровне в стеке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f66c-135">To use the custom message encoder in a WCF application, a binding element is required that creates the message encoder factory with the appropriate settings at the appropriate level in the run-time stack.</span></span>

<span data-ttu-id="1f66c-136">Класс `CustomTextMessageBindingElement` является производным от базового класса <xref:System.ServiceModel.Channels.BindingElement> и наследует от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1f66c-136">The `CustomTextMessageBindingElement` derives from the <xref:System.ServiceModel.Channels.BindingElement> base class and inherits from the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> class.</span></span> <span data-ttu-id="1f66c-137">Это позволяет другим компонентам WCF распознавать этот элемент привязки как элемент привязки кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="1f66c-137">This allows other WCF components to recognize this binding element as being a message encoding binding element.</span></span> <span data-ttu-id="1f66c-138">Реализация <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> возвращает экземпляр соответствующей фабрики кодировщиков сообщений с соответствующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="1f66c-138">The implementation of <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> returns an instance of the matching message encoder factory with appropriate settings.</span></span>

<span data-ttu-id="1f66c-139">Элемент `CustomTextMessageBindingElement` предоставляет параметры для `MessageVersion`, `ContentType` и `Encoding` через свойства.</span><span class="sxs-lookup"><span data-stu-id="1f66c-139">The `CustomTextMessageBindingElement` exposes settings for `MessageVersion`, `ContentType`, and `Encoding` through properties.</span></span> <span data-ttu-id="1f66c-140">Кодировщик поддерживает версии Soap11Addressing и Soap12Addressing1.</span><span class="sxs-lookup"><span data-stu-id="1f66c-140">The encoder supports both Soap11Addressing and Soap12Addressing1 versions.</span></span> <span data-ttu-id="1f66c-141">Значение по умолчанию - Soap11Addressing1.</span><span class="sxs-lookup"><span data-stu-id="1f66c-141">The default is Soap11Addressing1.</span></span> <span data-ttu-id="1f66c-142">Значение по умолчанию `ContentType` - "text/xml".</span><span class="sxs-lookup"><span data-stu-id="1f66c-142">The default value of the `ContentType` is "text/xml".</span></span> <span data-ttu-id="1f66c-143">Свойство `Encoding` позволяет задать значение требуемой кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="1f66c-143">The `Encoding` property allows you to set the value of the desired character encoding.</span></span> <span data-ttu-id="1f66c-144">Пример клиента и службы использует кодировку символов ISO-8859-1 (Latin1), которая не поддерживается <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> из WCF.</span><span class="sxs-lookup"><span data-stu-id="1f66c-144">The sample client and service uses the ISO-8859-1 (Latin1) character encoding, which is not supported by the <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF.</span></span>

<span data-ttu-id="1f66c-145">В следующем коде показано, как программным способом создать привязку, использующую пользовательский кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="1f66c-145">The following code shows how to programmatically create the binding using the custom text message encoder.</span></span>

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a><span data-ttu-id="1f66c-146">Добавление поддержки метаданных в элемент привязки кодирования сообщений</span><span class="sxs-lookup"><span data-stu-id="1f66c-146">Adding Metadata Support to the Message Encoding Binding Element</span></span>

<span data-ttu-id="1f66c-147">Любой тип, унаследованный от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>, отвечает за обновление версии привязки протокола SOAP в документе WSDL, созданном для службы.</span><span class="sxs-lookup"><span data-stu-id="1f66c-147">Any type that derives from <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> is responsible for updating the version of the SOAP binding in the WSDL document generated for the service.</span></span> <span data-ttu-id="1f66c-148">Этого можно добиться, реализовав метод `ExportEndpoint` в интерфейсе <xref:System.ServiceModel.Description.IWsdlExportExtension>, а затем изменив созданный язык WSDL.</span><span class="sxs-lookup"><span data-stu-id="1f66c-148">This is done by implementing the `ExportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlExportExtension> interface and then modifying the generated WSDL.</span></span> <span data-ttu-id="1f66c-149">В этом образце `CustomTextMessageBindingElement` использует логику экспорта WSDL из `TextMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="1f66c-149">In this sample, the `CustomTextMessageBindingElement` uses the WSDL export logic from the `TextMessageEncodingBindingElement`.</span></span>

<span data-ttu-id="1f66c-150">В этом образце конфигурация клиента настраивается вручную.</span><span class="sxs-lookup"><span data-stu-id="1f66c-150">For this sample, the client configuration is hand configured.</span></span> <span data-ttu-id="1f66c-151">Для создания конфигурации клиента нельзя использовать средство Svcutil.exe, так как элемент `CustomTextMessageBindingElement` не экспортирует утверждение политики для описания своего поведения.</span><span class="sxs-lookup"><span data-stu-id="1f66c-151">You cannot use Svcutil.exe to generate the client configuration because the `CustomTextMessageBindingElement` does not export a policy assertion to describe its behavior.</span></span> <span data-ttu-id="1f66c-152">Обычно необходимо реализовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в пользовательском элементе привязки для экспорта пользовательского утверждения политики, которое описывает поведение или возможности, реализуемые элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="1f66c-152">You should generally implement the <xref:System.ServiceModel.Description.IPolicyExportExtension> interface on a custom binding element to export a custom policy assertion that describes the behavior or capability implemented by the binding element.</span></span> <span data-ttu-id="1f66c-153">Пример экспорта утверждения политика для пользовательского элемента привязки, см. в разделе [транспорта: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="1f66c-153">For an example of how to export a policy assertion for a custom binding element, see the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>

## <a name="message-encoding-binding-configuration-handler"></a><span data-ttu-id="1f66c-154">Обработчик конфигурации привязки кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="1f66c-154">Message Encoding Binding Configuration Handler</span></span>
<span data-ttu-id="1f66c-155">В предыдущем разделе показано, как использовать пользовательский кодировщик текстовых сообщений программно.</span><span class="sxs-lookup"><span data-stu-id="1f66c-155">The previous section shows how to use the custom text message encoder programmatically.</span></span> <span data-ttu-id="1f66c-156">`CustomTextMessageEncodingBindingSection` реализует обработчик конфигурации, позволяющий задать использование пользовательского кодировщика текстовых сообщений в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f66c-156">The `CustomTextMessageEncodingBindingSection` implements a configuration handler that allows you to specify the use of a custom text message encoder within a configuration file.</span></span> <span data-ttu-id="1f66c-157">Класс `CustomTextMessageEncodingBindingSection` является производным от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> .</span><span class="sxs-lookup"><span data-stu-id="1f66c-157">The `CustomTextMessageEncodingBindingSection` class derives from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="1f66c-158">Свойство `BindingElementType` информирует систему конфигурации о типе элемента привязки, который следует создать для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1f66c-158">The `BindingElementType` property informs the configuration system of the type of binding element to create for this section.</span></span>

<span data-ttu-id="1f66c-159">Все параметры, определенные элементом `CustomTextMessageBindingElement`, представляются в виде свойств в разделе `CustomTextMessageEncodingBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="1f66c-159">All of the settings defined by `CustomTextMessageBindingElement` are exposed as the properties in the `CustomTextMessageEncodingBindingSection`.</span></span> <span data-ttu-id="1f66c-160">Атрибут <xref:System.Configuration.ConfigurationPropertyAttribute> помогает при сопоставлении атрибутов элемента конфигурации со свойствами и при задании значений по умолчанию, если атрибут не задан.</span><span class="sxs-lookup"><span data-stu-id="1f66c-160">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if the attribute is not set.</span></span> <span data-ttu-id="1f66c-161">После того как значения из конфигурации загружены и применены к свойствам нужного типа, вызывается метод <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>, который преобразует свойства в конкретный экземпляр элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="1f66c-161">After the values from configuration are loaded and applied to the properties of the type, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span>

<span data-ttu-id="1f66c-162">Этот обработчик конфигурации сопоставляет следующее представление в файле App.config или Web.config для службы или клиента.</span><span class="sxs-lookup"><span data-stu-id="1f66c-162">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />
```

<span data-ttu-id="1f66c-163">В образце используется кодировка ISO-8859-1.</span><span class="sxs-lookup"><span data-stu-id="1f66c-163">The sample uses the ISO-8859-1 encoding.</span></span>

<span data-ttu-id="1f66c-164">Для использования этого обработчика конфигурации его необходимо зарегистрировать с помощью приведенного ниже элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1f66c-164">To use this configuration handler it must be registered using the following configuration element.</span></span>

```xml
<extensions>
    <bindingElementExtensions>
        <add name="customTextMessageEncoding" type=" 
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection, 
                  CustomTextMessageEncoder" />
    </bindingElementExtensions>
</extensions>
```
