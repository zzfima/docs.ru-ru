---
title: 'Пользовательский кодировщик сообщений: пользовательский кодировщик текста — WCF'
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 3d421aa40488deac487418b5ecc83c5dd420fdf4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281686"
---
# <a name="custom-message-encoder-custom-text-encoder"></a>Пользовательский кодировщик сообщений: кодировщик пользовательских текстовых сообщений

В этом примере демонстрируется реализация пользовательского кодировщика текстовых сообщений с помощью Windows Communication Foundation (WCF).

> [!WARNING]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
> 
> `<InstallDrive>:\WF_WCF_Samples`
> 
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF поддерживает только кодировки Юникода UTF-8, UTF-16 и Big-endian с обратным порядком байтов. Кодировщик настраиваемых текстовых сообщений в этом примере поддерживает все кодировки символов, поддерживаемые платформой, которые могут потребоваться для взаимодействия. Пример состоит из клиентской консоли (exe), библиотеки служб (. dll), размещенной службы IIS (IIS), и библиотеки кодировщика текстовых сообщений (. dll). Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (добавить, вычесть, умножить и разделить). Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат. Как клиент, так и служба используют кодировщик `CustomTextMessageEncoder` вместо кодировщика по умолчанию <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.

Реализация пользовательского кодировщика состоит из фабрики кодировщиков сообщений, кодировщика сообщений, элемента привязки кодировщика сообщений и обработчика конфигурации. При этом демонстрируются следующие операции.

- Построение пользовательского кодировщика и фабрики кодировщика.

- Создание элемента привязки для пользовательского кодировщика.

- Использование конфигурации пользовательской привязки для интеграции элементов пользовательской привязки.

- Разработка обработчика пользовательской конфигурации для обеспечения настройки элемента пользовательской привязки в файле.

## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Установите ASP.NET 4,0 с помощью следующей команды.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

3. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

## <a name="message-encoder-factory-and-the-message-encoder"></a>Фабрика кодировщика сообщений и кодировщик сообщений

При открытии <xref:System.ServiceModel.ServiceHost> или канала клиента компонент времени разработки `CustomTextMessageBindingElement` создает фабрику `CustomTextMessageEncoderFactory`. Фабрика создает кодировщик `CustomTextMessageEncoder`. Кодировщик сообщений работает как в режиме буферизации, так и в режиме потоковой передачи. Он использует классы <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter> для чтения и записи сообщений соответственно. В отличие от оптимизированных средств чтения и записи XML WCF, которые поддерживают только кодировку UTF-8, UTF-16 и Юникод с обратным порядком байтов, эти средства чтения и записи поддерживают всю поддерживаемую платформой кодирование.

В следующем примере кода показан кодировщик CustomTextMessageEncoder.

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

В следующем примере кода показано, как построить фабрику кодировщиков сообщений.

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

## <a name="message-encoding-binding-element"></a>Элемент привязки кодирования сообщений

Элементы привязки позволяют настроить стек времени выполнения WCF. Чтобы использовать пользовательский кодировщик сообщений в приложении WCF, требуется элемент привязки, который создает фабрику кодировщиков сообщений с соответствующими параметрами на соответствующем уровне в стеке времени выполнения.

Класс `CustomTextMessageBindingElement` является производным от базового класса <xref:System.ServiceModel.Channels.BindingElement> и наследует от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>. Это позволяет другим компонентам WCF распознать этот элемент привязки как элемент привязки кодирования сообщений. Реализация <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> возвращает экземпляр соответствующей фабрики кодировщиков сообщений с соответствующими параметрами.

Элемент `CustomTextMessageBindingElement` предоставляет параметры для `MessageVersion`, `ContentType` и `Encoding` через свойства. Кодировщик поддерживает версии Soap11Addressing и Soap12Addressing1. Значение по умолчанию - Soap11Addressing1. Значение по умолчанию `ContentType` - "text/xml". Свойство `Encoding` позволяет задать значение требуемой кодировки символов. В примере клиента и службы используется кодировка ISO-8859-1 (Latin1), которая не поддерживается <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF.

В следующем коде показано, как программным способом создать привязку, использующую пользовательский кодировщик текстовых сообщений.

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a>Добавление поддержки метаданных в элемент привязки кодирования сообщений

Любой тип, унаследованный от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>, отвечает за обновление версии привязки протокола SOAP в документе WSDL, созданном для службы. Этого можно добиться, реализовав метод `ExportEndpoint` в интерфейсе <xref:System.ServiceModel.Description.IWsdlExportExtension>, а затем изменив созданный язык WSDL. В этом образце `CustomTextMessageBindingElement` использует логику экспорта WSDL из `TextMessageEncodingBindingElement`.

В этом образце конфигурация клиента настраивается вручную. Для создания конфигурации клиента нельзя использовать средство Svcutil.exe, так как элемент `CustomTextMessageBindingElement` не экспортирует утверждение политики для описания своего поведения. Обычно необходимо реализовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в пользовательском элементе привязки для экспорта пользовательского утверждения политики, которое описывает поведение или возможности, реализуемые элементом привязки. Пример экспорта утверждения политики для пользовательского элемента привязки см. в примере [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) .

## <a name="message-encoding-binding-configuration-handler"></a>Обработчик конфигурации привязки кодировщика сообщений
В предыдущем разделе показано, как использовать пользовательский кодировщик текстовых сообщений программно. `CustomTextMessageEncodingBindingSection` реализует обработчик конфигурации, позволяющий задать использование пользовательского кодировщика текстовых сообщений в файле конфигурации. Класс `CustomTextMessageEncodingBindingSection` является производным от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> . Свойство `BindingElementType` информирует систему конфигурации о типе элемента привязки, который следует создать для этого раздела.

Все параметры, определенные элементом `CustomTextMessageBindingElement`, представляются в виде свойств в разделе `CustomTextMessageEncodingBindingSection`. Атрибут <xref:System.Configuration.ConfigurationPropertyAttribute> помогает при сопоставлении атрибутов элемента конфигурации со свойствами и при задании значений по умолчанию, если атрибут не задан. После того как значения из конфигурации загружены и применены к свойствам нужного типа, вызывается метод <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>, который преобразует свойства в конкретный экземпляр элемента привязки.

Этот обработчик конфигурации сопоставляет следующее представление в файле App.config или Web.config для службы или клиента.

```xml
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />
```

В образце используется кодировка ISO-8859-1.

Для использования этого обработчика конфигурации его необходимо зарегистрировать с помощью приведенного ниже элемента конфигурации.

```xml
<extensions>
    <bindingElementExtensions>
        <add name="customTextMessageEncoding" type=" 
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection, 
                  CustomTextMessageEncoder" />
    </bindingElementExtensions>
</extensions>
```
