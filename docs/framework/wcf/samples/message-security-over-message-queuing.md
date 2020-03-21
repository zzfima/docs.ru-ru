---
title: Безопасность сообщений при использовании очереди сообщений
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: 2048b27f15787c70abda65ae582849276469c763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144439"
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="c5b07-102">Безопасность сообщений при использовании очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="c5b07-102">Message Security over Message Queuing</span></span>
<span data-ttu-id="c5b07-103">В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера через MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c5b07-103">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="c5b07-104">В некоторых случаях безопасность сообщений применяется, чтобы гарантировать, что сообщения в хранилище MSMQ остаются зашифрованными, а приложение может осуществлять собственную проверку подлинности сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5b07-104">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>

 <span data-ttu-id="c5b07-105">Этот образец основан на [транс-образной пробы Связывания МСМЗ.](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)</span><span class="sxs-lookup"><span data-stu-id="c5b07-105">This sample is based on the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="c5b07-106">Сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="c5b07-106">The messages are encrypted and signed.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c5b07-107">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c5b07-107">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c5b07-108">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="c5b07-108">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c5b07-109">При первом запуске служба проверит наличие очереди.</span><span class="sxs-lookup"><span data-stu-id="c5b07-109">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="c5b07-110">Если очередь отсутствует, служба ее создаст.</span><span class="sxs-lookup"><span data-stu-id="c5b07-110">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="c5b07-111">Можно сначала запустить службу, чтобы создать очередь, либо создать ее с помощью диспетчера очередей MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c5b07-111">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="c5b07-112">Чтобы создать очередь в Windows 2008, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="c5b07-112">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="c5b07-113">Открытый менеджер сервера в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="c5b07-113">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="c5b07-114">Расширьте вкладку **«Функции».**</span><span class="sxs-lookup"><span data-stu-id="c5b07-114">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="c5b07-115">Справа щелкните **Очереди частных сообщений**и выберите **Новый,** **Частный Конвей**.</span><span class="sxs-lookup"><span data-stu-id="c5b07-115">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="c5b07-116">Проверьте **транзакционную** коробку.</span><span class="sxs-lookup"><span data-stu-id="c5b07-116">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="c5b07-117">Введите `ServiceModelSamplesTransacted` как имя новой очереди.</span><span class="sxs-lookup"><span data-stu-id="c5b07-117">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="c5b07-118">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5b07-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c5b07-119">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="c5b07-119">To run the sample on the same computer</span></span>

1. <span data-ttu-id="c5b07-120">Убедитесь, что путь включает папку, в которой содержатся файлы Makecert.exe и FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="c5b07-120">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>

2. <span data-ttu-id="c5b07-121">Запустите файл Setup.bat из папки установки примера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-121">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="c5b07-122">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="c5b07-122">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5b07-123">После завершения работы образца выполните в папке образца файл Cleanup.bat, чтобы удалить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="c5b07-123">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="c5b07-124">В других образцах обеспечения безопасности используются те же сертификаты.</span><span class="sxs-lookup"><span data-stu-id="c5b07-124">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="c5b07-125">Запустите программу Service.exe из каталога \service\bin.</span><span class="sxs-lookup"><span data-stu-id="c5b07-125">Launch Service.exe from \service\bin.</span></span>  
  
4. <span data-ttu-id="c5b07-126">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="c5b07-126">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c5b07-127">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-127">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="c5b07-128">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c5b07-128">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c5b07-129">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="c5b07-129">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="c5b07-130">Скопируйте файлы Setup.bat, Cleanup.bat и ImportClientCert.bat на компьютер службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-130">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2. <span data-ttu-id="c5b07-131">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-131">Create a directory on the client computer for the client binaries.</span></span>  
  
3. <span data-ttu-id="c5b07-132">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-132">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="c5b07-133">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="c5b07-133">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4. <span data-ttu-id="c5b07-134">На сервере выполните команду `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="c5b07-134">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="c5b07-135">Запуск `setup.bat` с `service` аргументом создает сертификат обслуживания с полностью квалифицированным доменным именем компьютера и экспортирует сертификат службы в файл под названием Service.cer.</span><span class="sxs-lookup"><span data-stu-id="c5b07-135">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5. <span data-ttu-id="c5b07-136">Отодеть сервис service.exe.config, чтобы отразить новое `findValue` имя сертификата (в атрибуте в [ \<сервисеСертификат>), ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)который является таким же, как полностью квалифицированное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-136">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6. <span data-ttu-id="c5b07-137">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="c5b07-137">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7. <span data-ttu-id="c5b07-138">На клиенте выполните команду `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="c5b07-138">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="c5b07-139">При выполнении команды `setup.bat`с аргументом `client` создается сертификат клиента с именем client.com, который экспортируется в файл с именем Client.cer.</span><span class="sxs-lookup"><span data-stu-id="c5b07-139">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8. <span data-ttu-id="c5b07-140">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-140">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="c5b07-141">Для этого замените имя localhost полным доменным именем сервера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-141">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="c5b07-142">Кроме того, необходимо изменить имя сертификата службы, чтобы оно совпадало с полным именем домена компьютера службы (в атрибуте `findValue` элемента `defaultCertificate` элемента `serviceCertificate` элемента `clientCredentials`).</span><span class="sxs-lookup"><span data-stu-id="c5b07-142">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="c5b07-143">Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="c5b07-143">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="c5b07-144">На клиенте выполните команду `ImportServiceCert.bat`.</span><span class="sxs-lookup"><span data-stu-id="c5b07-144">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="c5b07-145">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="c5b07-145">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="c5b07-146">На сервере запустите файл `ImportClientCert.bat`. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="c5b07-146">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="c5b07-147">На компьютере службы запустите из командной строки программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="c5b07-147">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="c5b07-148">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="c5b07-148">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="c5b07-149">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c5b07-149">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c5b07-150">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="c5b07-150">To clean up after the sample</span></span>  
  
- <span data-ttu-id="c5b07-151">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="c5b07-151">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c5b07-152">Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="c5b07-152">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="c5b07-153">Если вы используете образцы Windows Communication Foundation (WCF), которые используют сертификаты на всех компьютерах, обязательно очистите сертификаты службы, установленные в магазине CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="c5b07-153">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="c5b07-154">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="c5b07-154">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c5b07-155">Требования</span><span class="sxs-lookup"><span data-stu-id="c5b07-155">Requirements</span></span>
 <span data-ttu-id="c5b07-156">Для этого образца необходимо установить и запустить MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c5b07-156">This sample requires that MSMQ is installed and running.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c5b07-157">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="c5b07-157">Demonstrates</span></span>
 <span data-ttu-id="c5b07-158">Клиент шифрует сообщение с использованием открытого ключа службы и подписывает сообщение с помощью своего сертификата.</span><span class="sxs-lookup"><span data-stu-id="c5b07-158">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="c5b07-159">Служба, считывающая сообщение из очереди, проверяет подлинность сертификата клиента с использованием сертификата в своем хранилище доверенных лиц.</span><span class="sxs-lookup"><span data-stu-id="c5b07-159">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="c5b07-160">Затем она расшифровывает сообщение и перенаправляет сообщение операции службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-160">It then decrypts the message and dispatches the message to the service operation.</span></span>

 <span data-ttu-id="c5b07-161">Поскольку сообщение Фонда связи Windows (WCF) переносится в виде полезной нагрузки в теле сообщения МСМЗ, тело остается зашифрованным в магазине МСМЗ.</span><span class="sxs-lookup"><span data-stu-id="c5b07-161">Because the Windows Communication Foundation (WCF) message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="c5b07-162">Это защищает сообщение от нежелательного раскрытия информации.</span><span class="sxs-lookup"><span data-stu-id="c5b07-162">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="c5b07-163">Обратите внимание, что сама служба MSMQ не содержит сведений о том, зашифрованы ли передаваемые через нее сообщения.</span><span class="sxs-lookup"><span data-stu-id="c5b07-163">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>

 <span data-ttu-id="c5b07-164">В этом образце показано, как использовать проверку подлинности на уровне сообщений в MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c5b07-164">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="c5b07-165">Обмен сертификатами осуществляется по внешним каналам.</span><span class="sxs-lookup"><span data-stu-id="c5b07-165">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="c5b07-166">Это всегда имеет место в случае использования приложением очередей, поскольку клиенту и службе не обязательно быть запущенными и работать одновременно.</span><span class="sxs-lookup"><span data-stu-id="c5b07-166">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>

## <a name="description"></a><span data-ttu-id="c5b07-167">Описание</span><span class="sxs-lookup"><span data-stu-id="c5b07-167">Description</span></span>
 <span data-ttu-id="c5b07-168">Пример клиента и сервисный код совпадают с [трансепробным образцом Связывания МСМ з](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) с одним отличием.</span><span class="sxs-lookup"><span data-stu-id="c5b07-168">The sample client and service code are the same as the [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="c5b07-169">Для контракта операции в виде заметки задается уровень защиты, который предполагает, что сообщение должно подписываться и шифроваться.</span><span class="sxs-lookup"><span data-stu-id="c5b07-169">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="c5b07-170">Чтобы сообщение защищалось с помощью маркера, позволяющего идентифицировать службу и клиент, файл App.config содержит учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c5b07-170">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>

 <span data-ttu-id="c5b07-171">В конфигурации клиента задается сертификат службы, который служит для проверки подлинности службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-171">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="c5b07-172">В качестве доверенного хранилища используется хранилище LocalMachine, чтобы можно было полагаться на допустимость службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-172">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="c5b07-173">Кроме того, задается сертификат клиента, который прикрепляется к сообщению с целью проверки подлинности клиента службой.</span><span class="sxs-lookup"><span data-stu-id="c5b07-173">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="c5b07-174">Обратите внимание, что задан режим безопасности Message, а атрибут ClientCredentialType имеет значение Certificate.</span><span class="sxs-lookup"><span data-stu-id="c5b07-174">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>

 <span data-ttu-id="c5b07-175">Конфигурация службы включает поведение службы, которое задает учетные данные службы, которые используются при проверке подлинности службы на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-175">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="c5b07-176">Имя предмета сертификата сервера указано в атрибуте `findValue` [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)в>.</span><span class="sxs-lookup"><span data-stu-id="c5b07-176">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </clientCertificate>
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

 <span data-ttu-id="c5b07-177">В этом образце демонстрируется управление проверкой подлинности с помощью файла конфигурации, а также получение удостоверения вызывающей стороны из контекста безопасности, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="c5b07-177">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 <span data-ttu-id="c5b07-178">При выполнении код службы выводит удостоверение клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-178">When run, the service code displays the client identification.</span></span> <span data-ttu-id="c5b07-179">Ниже показан образец результатов выполнения кода службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-179">The following is a sample output from the service code:</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a><span data-ttu-id="c5b07-180">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c5b07-180">Comments</span></span>

- <span data-ttu-id="c5b07-181">Создание сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-181">Creating the client certificate.</span></span>

     <span data-ttu-id="c5b07-182">Следующая строка пакетного файла создает сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-182">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="c5b07-183">В качестве имени субъекта создаваемого сертификата используется указанное имя клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-183">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="c5b07-184">Сертификат сохраняется в хранилище `My` в расположении `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="c5b07-184">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="c5b07-185">Установка сертификата клиента в хранилище доверенных сертификатов сервера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-185">Installing the client certificate into server’s trusted certificate store.</span></span>

     <span data-ttu-id="c5b07-186">Следующая строка пакетного файла копирует сертификат клиента в хранилище TrustedPeople сервера, чтобы сервер мог принимать соответствующие решения о доверии или недоверии.</span><span class="sxs-lookup"><span data-stu-id="c5b07-186">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="c5b07-187">Для того чтобы сертификат, установленный в магазине TrustedPeople, был доверен службе Windows Communication `PeerOrChainTrust` Foundation `PeerTrust` (WCF), режим проверки сертификата клиента должен быть установлен или определен.</span><span class="sxs-lookup"><span data-stu-id="c5b07-187">For a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="c5b07-188">Чтобы узнать, как это сделать с помощью файла конфигурации, см. приведенный выше образец конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-188">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="c5b07-189">Создание сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-189">Creating the server certificate.</span></span>

     <span data-ttu-id="c5b07-190">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-190">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="c5b07-191">Переменная %SERVER_NAME% задает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="c5b07-191">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="c5b07-192">Сертификат хранится в хранилище LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c5b07-192">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="c5b07-193">Если пакетный файл настройки работает с аргументом `setup.bat service`службы (например, % SERVER_NAME% содержит полностью квалифицированное доменное имя компьютера. В противном случае он по умолчанию локального хозяина</span><span class="sxs-lookup"><span data-stu-id="c5b07-193">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>

- <span data-ttu-id="c5b07-194">Установка сертификата сервера в хранилище доверенных сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-194">Installing server certificate into the client’s trusted certificate store.</span></span>

     <span data-ttu-id="c5b07-195">Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="c5b07-195">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c5b07-196">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-196">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c5b07-197">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="c5b07-197">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="c5b07-198">Если используется выпуск Microsoft Windows на языке, отличном от английского (США), необходимо изменить файл Setup.bat и заменить имя учетной записи "NT AUTHORITY\NETWORK SERVICE" эквивалентом соответствующего языка.</span><span class="sxs-lookup"><span data-stu-id="c5b07-198">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5b07-199">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c5b07-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c5b07-200">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c5b07-200">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c5b07-201">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="c5b07-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c5b07-202">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c5b07-202">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
