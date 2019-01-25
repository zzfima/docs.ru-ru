---
title: Как выполнить Создание пользовательской привязки надежного сеанса с использованием HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516685"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="0c987-102">Как выполнить Создание пользовательской привязки надежного сеанса с использованием HTTPS</span><span class="sxs-lookup"><span data-stu-id="0c987-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="0c987-103">В этом разделе рассматривается использование механизма обеспечения безопасности транспорта через протокол SSL и надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="0c987-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="0c987-104">Для использования надежных сеансов через протокол HTTPS требуется создать пользовательскую привязку, использующую надежный сеанс и транспорт HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0c987-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="0c987-105">Как разрешить надежный сеанс можно принудительно с помощью кода или декларативно в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c987-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="0c987-106">Эта процедура использует файлы конфигурации клиента и службы для разрешения надежного сеанса и [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0c987-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="0c987-107">Ключевой частью этой процедуры является то, что  **\<конечной точки >** элемент конфигурации содержит `bindingConfiguration` атрибут, который ссылается на пользовательскую конфигурацию привязки с именем `reliableSessionOverHttps`.</span><span class="sxs-lookup"><span data-stu-id="0c987-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="0c987-108">[  **\<Привязки >** ](../../../../docs/framework/misc/binding.md) элемент конфигурации ссылается на это имя, чтобы указать, надежный сеанс и транспорт HTTPS используются в том числе  **\< reliableSession >** и  **\<httpsTransport >** элементов.</span><span class="sxs-lookup"><span data-stu-id="0c987-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="0c987-109">Копию исходного кода в этом примере, см. в разделе [пользовательские привязки надежного сеанса по протоколу HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="0c987-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0c987-110">Настройка службы с привязкой CustomBinding использования надежного сеанса с помощью протокола HTTPS</span><span class="sxs-lookup"><span data-stu-id="0c987-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0c987-111">Определите контракт службы для данного типа службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="0c987-112">Реализуйте контракт службы в классе службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="0c987-113">Обратите внимание на то, что информация об адресе или привязке не указывается внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0c987-114">Не требуется писать код для извлечения информации адресе или привязке из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c987-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="0c987-115">Создание *Web.config* файл, чтобы настроить конечную точку для `CalculatorService` с пользовательской привязки с именем `reliableSessionOverHttps` , использующий надежный сеанс и транспорт HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0c987-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="0c987-116">Создание *Service.svc* файл, содержащий строку:</span><span class="sxs-lookup"><span data-stu-id="0c987-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="0c987-117">Место *Service.svc* файла в виртуальный каталог Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0c987-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0c987-118">Настройка клиента с привязкой CustomBinding использования надежного сеанса с помощью протокола HTTPS</span><span class="sxs-lookup"><span data-stu-id="0c987-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0c987-119">Используйте [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="0c987-120">Создаваемый клиент содержит `ICalculator` интерфейс, определяющий контракт службы, должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="0c987-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="0c987-121">Созданное клиентское приложение также содержит реализацию `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="0c987-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="0c987-122">Обратите внимание на то, что сведения об адресе и привязке не указывается внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0c987-123">Не требуется писать код, чтобы получить адрес и сведения о привязке из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0c987-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="0c987-124">Настроить пользовательскую привязку с именем `reliableSessionOverHttps` использовать транспорт HTTPS и надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="0c987-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="0c987-125">Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="0c987-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="0c987-126">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="0c987-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="0c987-127">безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c987-127">.NET Framework security</span></span>

<span data-ttu-id="0c987-128">Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным с помощью *Makecert.exe*, появляется предупреждение системы безопасности, при попытке доступа к адресу HTTPS, таким как `https://localhost/servicemodelsamples/service.svc`, в браузере.</span><span class="sxs-lookup"><span data-stu-id="0c987-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c987-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0c987-129">See also</span></span>

- [<span data-ttu-id="0c987-130">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="0c987-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
