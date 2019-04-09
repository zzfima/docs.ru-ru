---
title: 'Пользовательский кодировщик сообщений: кодировщик сжатия'
ms.date: 03/30/2017
ms.assetid: 57450b6c-89fe-4b8a-8376-3d794857bfd7
ms.openlocfilehash: 9dd1e2eb25b2f400ba42b6cee75f8563c4d52c31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140690"
---
# <a name="custom-message-encoder-compression-encoder"></a><span data-ttu-id="ed0c8-102">Пользовательский кодировщик сообщений: кодировщик сжатия</span><span class="sxs-lookup"><span data-stu-id="ed0c8-102">Custom Message Encoder: Compression Encoder</span></span>
<span data-ttu-id="ed0c8-103">В этом примере показано, как реализовать пользовательский кодировщик с помощью платформы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-103">This sample demonstrates how to implement a custom encoder using the Windows Communication Foundation (WCF) platform.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed0c8-104">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed0c8-105">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed0c8-106">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed0c8-107">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`  
  
## <a name="sample-details"></a><span data-ttu-id="ed0c8-108">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="ed0c8-108">Sample Details</span></span>  
 <span data-ttu-id="ed0c8-109">Пример содержит консольную программу клиента (EXE), консольную программу резидентной службы (EXE) и библиотеку кодировщика сжатия сообщений (DLL).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-109">This sample consists of a client console program (.exe), a self-hosted service console program (.exe) and a compression message encoder library (.dll).</span></span> <span data-ttu-id="ed0c8-110">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="ed0c8-110">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="ed0c8-111">Контракт определяется интерфейсом `ISampleServer`, предоставляющим базовые операции отображения строк (`Echo` и `BigEcho`).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-111">The contract is defined by the `ISampleServer` interface, which exposes basic string echoing operations (`Echo` and `BigEcho`).</span></span> <span data-ttu-id="ed0c8-112">Клиент осуществляет синхронные вызовы заданной операции, а служба отвечает, снова отправляя это сообщение назад клиенту.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-112">The client makes synchronous requests to a given operation and the service replies by repeating the message back to the client.</span></span> <span data-ttu-id="ed0c8-113">Действия клиента и службы отображаются в окнах консолей.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-113">Client and service activity is visible in the console windows.</span></span> <span data-ttu-id="ed0c8-114">Этот образец предназначен для того, чтобы показать, как написать пользовательский кодировщик, и продемонстрировать влияние сжатия сообщения на передачу по сети.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-114">The intent of this sample is to show how to write a custom encoder and demonstrate the impact of compression of a message on the wire.</span></span> <span data-ttu-id="ed0c8-115">К кодировщику сжатия сообщений можно добавить инструментарий для вычисления размера сообщения, времени обработки или обоих этих параметров.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-115">You can add instrumentation to the compression message encoder to calculate message size, processing time, or both.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed0c8-116">В .NET Framework 4 автоматическая распаковка была включена на клиенте WCF при отправке сервером сжатого ответа (созданная с помощью такого алгоритма, как GZip или Deflate).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-116">In the .NET Framework 4, automatic decompression has been enabled on a WCF client if the server is sending a compressed response (created with an algorithm such as GZip or Deflate).</span></span> <span data-ttu-id="ed0c8-117">Если служба размещена на веб-сервере в службах IIS, то для службы IIS необходимо настроить отправку сжатого ответа.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-117">If the service is Web-hosted in Internet Information Server (IIS), then IIS can be configured for the service to send a compressed response.</span></span> <span data-ttu-id="ed0c8-118">Можно использовать этот образец, если служба является резидентной и сжатие и распаковка должны быть выполнены и на клиенте, и в службе.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-118">This sample can be used if the requirement is to do compression and decompression on both the client and the service or if the service is self-hosted.</span></span>  
  
 <span data-ttu-id="ed0c8-119">Образец демонстрирует и интегрировать пользовательский кодировщик сообщений в приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-119">The sample demonstrates how to build and integrate a custom message encoder into a WCF application.</span></span> <span data-ttu-id="ed0c8-120">Библиотека GZipEncoder.dll развертывается как с клиентом, так и со службой.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-120">The library GZipEncoder.dll is deployed with both the client and the service.</span></span> <span data-ttu-id="ed0c8-121">Этот образец также демонстрирует влияние сжатия сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-121">This sample also demonstrates the impact of compressing messages.</span></span> <span data-ttu-id="ed0c8-122">Код в библиотеке GZipEncoder.dll демонстрирует следующие операции.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-122">The code in GZipEncoder.dll demonstrates the following:</span></span>  
  
-   <span data-ttu-id="ed0c8-123">Построение пользовательского кодировщика и фабрики кодировщика.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-123">Building a custom encoder and encoder factory.</span></span>  
  
-   <span data-ttu-id="ed0c8-124">Разработка элемента привязки для пользовательского кодировщика.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-124">Developing a binding element for a custom encoder.</span></span>  
  
-   <span data-ttu-id="ed0c8-125">Использование конфигурации пользовательской привязки для интеграции элементов пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-125">Using the custom binding configuration for integrating custom binding elements.</span></span>  
  
-   <span data-ttu-id="ed0c8-126">Разработка обработчика пользовательской конфигурации для обеспечения настройки элемента пользовательской привязки в файле.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-126">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>  
  
 <span data-ttu-id="ed0c8-127">Как указывалось ранее, существуют несколько уровней, реализованных в пользовательском кодировщике.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-127">As indicated previously, there are several layers that are implemented in a custom encoder.</span></span> <span data-ttu-id="ed0c8-128">Чтобы лучше показать взаимоотношения между различными уровнями, ниже приведен упрощенный список событий для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-128">To better illustrate the relationship between each of these layers, a simplified order of events for service start-up is in the following list:</span></span>  
  
1.  <span data-ttu-id="ed0c8-129">Запускается служба.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-129">The server starts.</span></span>  
  
2.  <span data-ttu-id="ed0c8-130">Считывается информация о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-130">The configuration information is read.</span></span>  
  
    1.  <span data-ttu-id="ed0c8-131">Конфигурация службы регистрирует пользовательских обработчик конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-131">The service configuration registers the custom configuration handler.</span></span>  
  
    2.  <span data-ttu-id="ed0c8-132">Создается и открывается основное приложение для данной службы.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-132">The service host is created and opened.</span></span>  
  
    3.  <span data-ttu-id="ed0c8-133">Пользовательский элемент конфигурации создает и возвращает пользовательский элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-133">The custom configuration element creates and returns the custom binding element.</span></span>  
  
    4.  <span data-ttu-id="ed0c8-134">Пользовательский элемент привязки создает и возвращает фабрику кодировщиков сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-134">The custom binding element creates and returns a message encoder factory.</span></span>  
  
3.  <span data-ttu-id="ed0c8-135">Принимается сообщение.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-135">A message is received.</span></span>  
  
4.  <span data-ttu-id="ed0c8-136">Фабрика кодировщиков сообщений возвращает кодировщик сообщения для чтения сообщения и записи ответа.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-136">The message encoder factory returns a message encoder for reading in the message and writing out the response.</span></span>  
  
5.  <span data-ttu-id="ed0c8-137">Уровень кодировщика реализован как фабрика класса.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-137">The encoder layer is implemented as a class factory.</span></span> <span data-ttu-id="ed0c8-138">Для пользовательского кодировщика должна быть общедоступна только фабрика класса кодировщика.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-138">Only the encoder class factory must be publicly exposed for the custom encoder.</span></span> <span data-ttu-id="ed0c8-139">Объект фабрики возвращается элементом привязки при создании объекта <xref:System.ServiceModel.ServiceHost> или <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-139">The factory object is returned by the binding element when the <xref:System.ServiceModel.ServiceHost> or <xref:System.ServiceModel.ChannelFactory%601> object is created.</span></span> <span data-ttu-id="ed0c8-140">Кодировщики сообщений могут работать в режиме буферизации или в режиме потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-140">Message encoders can operate in a buffered or streaming mode.</span></span> <span data-ttu-id="ed0c8-141">В этом образце демонстрируется как режим буферизации, так и режим потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-141">This sample demonstrates both buffered mode and streaming mode.</span></span>  
  
 <span data-ttu-id="ed0c8-142">Для каждого режима имеются соответствующие методы `ReadMessage` и `WriteMessage` абстрактного класса `MessageEncoder`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-142">For each mode there is an accompanying `ReadMessage` and `WriteMessage` method on the abstract `MessageEncoder` class.</span></span> <span data-ttu-id="ed0c8-143">Большая часть работы по кодированию выполняется в этих методах.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-143">A majority of the encoding work takes place in these methods.</span></span> <span data-ttu-id="ed0c8-144">Данный образец выступает в роли оболочки существующих кодировщиков текстовых и двоичных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-144">The sample wraps the existing text and binary message encoders.</span></span> <span data-ttu-id="ed0c8-145">Это позволяет образецу делегировать внутреннему кодировщику чтение и запись сообщений в форме, передаваемой по сети, а кодировщику сжатия сжимать и распаковывать результаты.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-145">This allows the sample to delegate the reading and writing of the wire representation of messages to the inner encoder and allows the compression encoder to compress or decompress the results.</span></span> <span data-ttu-id="ed0c8-146">Из-за отсутствия конвейера для кодирования сообщений, это только модель использования нескольких кодировщиков в WCF.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-146">Because there is no pipeline for message encoding, this is the only model for using multiple encoders in WCF.</span></span> <span data-ttu-id="ed0c8-147">После того как сообщение распаковано, оно передается вверх стека для обработки стеком канала.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-147">Once the message has been decompressed, the resulting message is passed up the stack for the channel stack to handle.</span></span> <span data-ttu-id="ed0c8-148">Во время сжатия получающееся сжатое сообщение записывается непосредственно в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-148">During compression, the resulting compressed message is written directly to the stream provided.</span></span>  
  
 <span data-ttu-id="ed0c8-149">В этом образце используются вспомогательные методы (`CompressBuffer` и `DecompressBuffer`) для преобразования из буферов в потоки, чтобы использовать класс `GZipStream`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-149">This sample uses helper methods (`CompressBuffer` and `DecompressBuffer`) to perform conversion from buffers to streams to use the `GZipStream` class.</span></span>  
  
 <span data-ttu-id="ed0c8-150">Буферизованные классы `ReadMessage` и `WriteMessage` используют класс `BufferManager`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-150">The buffered `ReadMessage` and `WriteMessage` classes make use of the `BufferManager` class.</span></span> <span data-ttu-id="ed0c8-151">Кодировщик доступен только через фабрику кодировщиков.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-151">The encoder is accessible only through the encoder factory.</span></span> <span data-ttu-id="ed0c8-152">Абстрактный класс `MessageEncoderFactory` предоставляет свойство с именем `Encoder` для доступа к текущему кодировщику и метод с именем `CreateSessionEncoder` для создания кодировщика, поддерживающего сеансы.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-152">The abstract `MessageEncoderFactory` class provides a property named `Encoder` for accessing the current encoder and a method named `CreateSessionEncoder` for creating an encoder that supports sessions.</span></span> <span data-ttu-id="ed0c8-153">Такой кодировщик может использоваться в сценарии, в котором канал поддерживает сеансы и является упорядоченным и надежным.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-153">Such an encoder can be used in the scenario where the channel supports sessions, is ordered and is reliable.</span></span> <span data-ttu-id="ed0c8-154">Этот сценарий допускает в каждом сеансе оптимизацию данных, записанных в сеть.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-154">This scenario allows for optimization in each session of the data written to the wire.</span></span> <span data-ttu-id="ed0c8-155">Если это не требуется, не следует перегружать базовый метод.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-155">If this is not desired, the base method should not be overloaded.</span></span> <span data-ttu-id="ed0c8-156">Свойство `Encoder` обеспечивает механизм для доступа к кодировщику, не поддерживающему сеансы, и реализация по умолчанию метода `CreateSessionEncoder` возвращает значение этого свойства.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-156">The `Encoder` property provides a mechanism for accessing the session-less encoder and the default implementation of the `CreateSessionEncoder` method returns the value of the property.</span></span> <span data-ttu-id="ed0c8-157">Так как для обеспечения сжатия образец выступает в роли оболочки для существующих кодировщиков, реализация `MessageEncoderFactory` принимает фабрику `MessageEncoderFactory`, которая представляет фабрику внутреннего кодировщика.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-157">Because the sample wraps an existing encoder to provide compression, the `MessageEncoderFactory` implementation accepts a `MessageEncoderFactory` that represents the inner encoder factory.</span></span>  
  
 <span data-ttu-id="ed0c8-158">Теперь, когда кодировщик и фабрика кодировщиков определены, они могут использоваться с клиентом WCF и службой.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-158">Now that the encoder and encoder factory are defined, they can be used with a WCF client and service.</span></span> <span data-ttu-id="ed0c8-159">Однако необходимо добавить эти кодировщики в стек канала.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-159">However, these encoders must be added to the channel stack.</span></span> <span data-ttu-id="ed0c8-160">Чтобы добавить эту фабрику кодировщиков вручную, можно создать производные классы от классов <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.ChannelFactory%601> и переопределить методы `OnInitialize`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-160">You can derive classes from the <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.ChannelFactory%601> classes and override the `OnInitialize` methods to add this encoder factory manually.</span></span> <span data-ttu-id="ed0c8-161">Доступ к фабрике кодировщиков можно также предоставить через пользовательский элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-161">You can also expose the encoder factory through a custom binding element.</span></span>  
  
 <span data-ttu-id="ed0c8-162">Чтобы создать новый пользовательский элемент привязки, создайте класс, производный от класса <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-162">To create a new custom binding element, derive a class from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="ed0c8-163">Однако существует несколько типов элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-163">There are, however, several types of binding elements.</span></span> <span data-ttu-id="ed0c8-164">Чтобы обеспечить распознавание пользовательского элемента привязки в качестве элемента привязки кодирования сообщений, необходимо также реализовать класс <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-164">To ensure that the custom binding element is recognized as a message encoding binding element, you also must implement the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span></span> <span data-ttu-id="ed0c8-165">Класс <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> предоставляет метод для создания новой фабрики кодировщиков сообщений (`CreateMessageEncoderFactory`), реализованный для возврата экземпляра соответствующей фабрики кодировщиков сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-165">The <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> exposes a method for creating a new message encoder factory (`CreateMessageEncoderFactory`), which is implemented to return an instance of the matching message encoder factory.</span></span> <span data-ttu-id="ed0c8-166">Кроме того, класс <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> имеет свойство, указывающее версию адресации.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-166">Additionally, the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> has a property to indicate the addressing version.</span></span> <span data-ttu-id="ed0c8-167">Так как этот образец выступает в роли оболочки для существующих кодировщиков, реализация образца также создает оболочку для существующих элементов привязки кодировщиков, принимает элемент привязки внутреннего кодировщика в качестве параметра конструктора и предоставляет его через свойство.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-167">Because this sample wraps the existing encoders, the sample implementation also wraps the existing encoder binding elements and takes an inner encoder binding element as a parameter to the constructor and exposes it through a property.</span></span> <span data-ttu-id="ed0c8-168">В следующем образце кода показана реализация класса `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-168">The following sample code shows the implementation of the `GZipMessageEncodingBindingElement` class.</span></span>  
  
```  
public sealed class GZipMessageEncodingBindingElement   
                        : MessageEncodingBindingElement //BindingElement  
                        , IPolicyExportExtension  
{  
  
    //We use an inner binding element to store information   
    //required for the inner encoder.  
    MessageEncodingBindingElement innerBindingElement;  
  
        //By default, use the default text encoder as the inner encoder.  
        public GZipMessageEncodingBindingElement()  
            : this(new TextMessageEncodingBindingElement()) { }  
  
    public GZipMessageEncodingBindingElement(MessageEncodingBindingElement messageEncoderBindingElement)  
    {  
        this.innerBindingElement = messageEncoderBindingElement;  
    }  
  
    public MessageEncodingBindingElement InnerMessageEncodingBindingElement  
    {  
        get { return innerBindingElement; }  
        set { innerBindingElement = value; }  
    }  
  
    //Main entry point into the encoder binding element.   
    // Called by WCF to get the factory that creates the  
    //message encoder.  
    public override MessageEncoderFactory CreateMessageEncoderFactory()  
    {  
        return new   
GZipMessageEncoderFactory(innerBindingElement.CreateMessageEncoderFactory());  
    }  
  
    public override MessageVersion MessageVersion  
    {  
        get { return innerBindingElement.MessageVersion; }  
        set { innerBindingElement.MessageVersion = value; }  
    }  
  
    public override BindingElement Clone()  
    {  
        return new   
        GZipMessageEncodingBindingElement(this.innerBindingElement);  
    }  
  
    public override T GetProperty<T>(BindingContext context)  
    {  
        if (typeof(T) == typeof(XmlDictionaryReaderQuotas))  
        {  
            return innerBindingElement.GetProperty<T>(context);  
        }  
        else   
        {  
            return base.GetProperty<T>(context);  
        }  
    }  
  
    public override IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
    {  
        if (context == null)  
            throw new ArgumentNullException("context");  
  
        context.BindingParameters.Add(this);  
        return context.BuildInnerChannelFactory<TChannel>();  
    }  
  
    public override IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
    {  
        if (context == null)  
            throw new ArgumentNullException("context");  
  
        context.BindingParameters.Add(this);  
        return context.BuildInnerChannelListener<TChannel>();  
    }  
  
    public override bool CanBuildChannelListener<TChannel>(BindingContext context)  
    {  
        if (context == null)  
            throw new ArgumentNullException("context");  
  
        context.BindingParameters.Add(this);  
        return context.CanBuildInnerChannelListener<TChannel>();  
    }  
  
    void IPolicyExportExtension.ExportPolicy(MetadataExporter exporter, PolicyConversionContext policyContext)  
    {  
        if (policyContext == null)  
        {  
            throw new ArgumentNullException("policyContext");  
        }  
       XmlDocument document = new XmlDocument();  
       policyContext.GetBindingAssertions().Add(document.CreateElement(  
            GZipMessageEncodingPolicyConstants.GZipEncodingPrefix,  
            GZipMessageEncodingPolicyConstants.GZipEncodingName,  
            GZipMessageEncodingPolicyConstants.GZipEncodingNamespace));  
    }  
}  
```  
  
 <span data-ttu-id="ed0c8-169">Обратите внимание, что класс `GZipMessageEncodingBindingElement` реализует интерфейс `IPolicyExportExtension`, чтобы этот элемент привязки можно было экспортировать в виде политики в метаданных, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-169">Note that `GZipMessageEncodingBindingElement` class implements the `IPolicyExportExtension` interface, so that this binding element can be exported as a policy in metadata, as shown in the following example.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="BufferedHttpSampleServer_ISampleServer_policy">  
    <wsp:ExactlyOne>  
      <wsp:All>  
        <gzip:text xmlns:gzip=  
        "http://schemas.microsoft.com/ws/06/2004/mspolicy/netgzip1" />   
       <wsaw:UsingAddressing />   
     </wsp:All>  
   </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="ed0c8-170">Класс `GZipMessageEncodingBindingElementImporter` реализует интерфейс `IPolicyImportExtension`, этот класс импортирует политику для класса `GZipMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-170">The `GZipMessageEncodingBindingElementImporter` class implements the `IPolicyImportExtension` interface, this class imports policy for `GZipMessageEncodingBindingElement`.</span></span> <span data-ttu-id="ed0c8-171">Для импорта политик в файл конфигурации может использоваться средство Svcutil.exe; для обработки `GZipMessageEncodingBindingElement` в файл Svcutil.exe.config необходимо добавить следующие строки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-171">Svcutil.exe tool can be used to import policies to the configuration file, to handle `GZipMessageEncodingBindingElement`, the following should be added to Svcutil.exe.config.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="gzipMessageEncoding"   
          type=  
            "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </bindingElementExtensions>  
    </extensions>  
    <client>  
      <metadata>  
        <policyImporters>  
          <remove type=  
"System.ServiceModel.Channels.MessageEncodingBindingElementImporter, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
          <extension type=  
"Microsoft.ServiceModel.Samples.GZipMessageEncodingBindingElementImporter, GZipEncoder, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ed0c8-172">Обратите внимание, что имеется соответствующий элемент привязки для кодировщика сжатия, он может быть программно подключен к службе или клиенту путем создания нового пользовательского объекта привязки и добавления в него пользовательского элемента привязки, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-172">Now that there is a matching binding element for the compression encoder, it can be programmatically hooked into the service or client by constructing a new custom binding object and adding the custom binding element to it, as shown in the following sample code.</span></span>  
  
```  
ICollection<BindingElement> bindingElements = new List<BindingElement>();  
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();  
GZipMessageEncodingBindingElement compBindingElement = new GZipMessageEncodingBindingElement ();  
bindingElements.Add(compBindingElement);  
bindingElements.Add(httpBindingElement);  
CustomBinding binding = new CustomBinding(bindingElements);  
binding.Name = "SampleBinding";  
binding.Namespace = "http://tempuri.org/bindings";  
```  
  
 <span data-ttu-id="ed0c8-173">Хотя этого может быть достаточно для большинства пользовательских сценариев, поддержка конфигурации с помощью файлов критически важно, если служба будет размещена в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-173">While this may be sufficient for the majority of user scenarios, supporting a file configuration is critical if a service is to be Web-hosted.</span></span> <span data-ttu-id="ed0c8-174">Для поддержки сценариев с размещением в Интернете необходимо разработать пользовательский обработчик конфигурации, позволяющий настраивать пользовательский элемент привязки в файле.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-174">To support the Web-hosted scenario, you must develop a custom configuration handler to allow a custom binding element to be configurable in a file.</span></span>  
  
 <span data-ttu-id="ed0c8-175">Пользовательский обработчик для элемента привязки можно построить на основе системы конфигурации, предоставляемой [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed0c8-175">You can build a configuration handler for the binding element on top of the configuration system provided by the [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span> <span data-ttu-id="ed0c8-176">Обработчик конфигурации для элемента привязки должен наследовать от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-176">The configuration handler for the binding element must derive from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="ed0c8-177">Свойство `BindingElementType` используется для информирования системы конфигурации о типе элемента привязки, который следует создать для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-177">The `BindingElementType` property is used to inform the configuration system of the type of binding element to create for this section.</span></span> <span data-ttu-id="ed0c8-178">Все аспекты элемента `BindingElement`, допускающие установку, должны быть представлены как свойства класса, производного от <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-178">All aspects of the `BindingElement` that can be set should be exposed as properties in the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class.</span></span> <span data-ttu-id="ed0c8-179">Класс <xref:System.Configuration.ConfigurationPropertyAttribute> помогает при сопоставлении атрибутов элемента конфигурации со свойствами и задании значений по умолчанию в случае отсутствия атрибута.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-179">The <xref:System.Configuration.ConfigurationPropertyAttribute> is used to assist in mapping the configuration element attributes to the properties and setting default values if attributes are missing.</span></span> <span data-ttu-id="ed0c8-180">После того как значения из конфигурации загружены и применены к свойствам, вызывается метод <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>, который преобразует свойства в конкретный экземпляр элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-180">After the values from configuration are loaded and applied to the properties, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span> <span data-ttu-id="ed0c8-181">Метод <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A> используется для преобразования свойств класса, производного от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, в значения, задаваемые в новом созданном элементе привязки.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-181">The <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.ApplyConfiguration%2A> method is used to convert the properties on the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> derived class into the values to be set on the newlycreated binding element.</span></span>  
  
 <span data-ttu-id="ed0c8-182">В следующем образце кода показана реализация класса `GZipMessageEncodingElement`.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-182">The following sample code shows the implementation of the `GZipMessageEncodingElement`.</span></span>  
  
```  
public class GZipMessageEncodingElement : BindingElementExtensionElement  
{  
    public GZipMessageEncodingElement()  
    {  
    }  
  
//Called by the WCF to discover the type of binding element this   
//config section enables  
    public override Type BindingElementType  
    {  
        get { return typeof(GZipMessageEncodingBindingElement); }  
    }  
  
    //The only property we need to configure for our binding element is   
    //the type of inner encoder to use. Here, we support text and  
    //binary.  
    [ConfigurationProperty("innerMessageEncoding",   
                         DefaultValue = "textMessageEncoding")]  
    public string InnerMessageEncoding  
    {  
        get { return (string)base["innerMessageEncoding"]; }  
        set { base["innerMessageEncoding"] = value; }  
    }  
  
    //Called by the WCF to apply the configuration settings (the   
    //property above) to the binding element  
    public override void ApplyConfiguration(BindingElement bindingElement)  
    {  
        GZipMessageEncodingBindingElement binding =   
                (GZipMessageEncodingBindingElement)bindingElement;  
        PropertyInformationCollection propertyInfo =   
                    this.ElementInformation.Properties;  
        if (propertyInfo["innerMessageEncoding"].ValueOrigin !=   
                                     PropertyValueOrigin.Default)  
        {  
            switch (this.InnerMessageEncoding)  
            {  
                case "textMessageEncoding":  
                    binding.InnerMessageEncodingBindingElement =   
                      new TextMessageEncodingBindingElement();  
                    break;  
                case "binaryMessageEncoding":  
                    binding.InnerMessageEncodingBindingElement =   
                         new BinaryMessageEncodingBindingElement();  
                    break;  
            }  
        }  
    }  
  
    //Called by the WCF to create the binding element  
    protected override BindingElement CreateBindingElement()  
    {  
        GZipMessageEncodingBindingElement bindingElement =   
                new GZipMessageEncodingBindingElement();  
        this.ApplyConfiguration(bindingElement);  
        return bindingElement;  
    }  
}   
```  
  
 <span data-ttu-id="ed0c8-183">Этот обработчик конфигурации сопоставляет следующее представление в файле App.config или Web.config для службы или клиента.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-183">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>  
  
```xml  
<gzipMessageEncoding innerMessageEncoding="textMessageEncoding" />  
```  
  
 <span data-ttu-id="ed0c8-184">Чтобы использовать этот обработчик конфигурации, он должен быть зарегистрирован в [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-184">To use this configuration handler, it must be registered within the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, as shown in the following sample configuration.</span></span>  
  
```xml  
<extensions>  
    <bindingElementExtensions>  
       <add   
           name="gzipMessageEncoding"   
           type=  
           "Microsoft.ServiceModel.Samples.GZipMessageEncodingElement,  
           GZipEncoder, Version=1.0.0.0, Culture=neutral,   
           PublicKeyToken=null" />  
      </bindingElementExtensions>  
</extensions>  
```  
  
 <span data-ttu-id="ed0c8-185">При работе службы запросы и ответы операции отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-185">When you run the server, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="ed0c8-186">Чтобы закрыть службу, нажмите клавишу ВВОД в этом окне.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-186">Press ENTER in the window to shut down the server.</span></span>  
  
```  
Press Enter key to Exit.  
  
        Server Echo(string input) called:  
        Client message: Simple hello  
  
        Server BigEcho(string[] input) called:  
        64 client messages  
```  
  
 <span data-ttu-id="ed0c8-187">При выполнении клиента запросы и ответы операции отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-187">When you run the client, the operation requests and responses are displayed in the console window.</span></span> <span data-ttu-id="ed0c8-188">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-188">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Calling Echo(string):  
Server responds: Simple hello Simple hello  
  
Calling BigEcho(string[]):  
Server responds: Hello 0  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ed0c8-189">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ed0c8-189">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ed0c8-190">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-190">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command:</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="ed0c8-191">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-191">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="ed0c8-192">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-192">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="ed0c8-193">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-193">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed0c8-194">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-194">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed0c8-195">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ed0c8-195">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed0c8-196">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-196">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed0c8-197">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ed0c8-197">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Compression`  
