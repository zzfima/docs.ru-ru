---
title: Гибкость шифрования в безопасности WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714926"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="6fdc1-102">Гибкость шифрования в безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="6fdc1-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="6fdc1-103">В этом примере показано, как указать в стандартном или пользовательском алгоритме, чтобы обеспечить динамическую реализацию в клиенте Windows Communication Foundation (WCF) и службе.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="6fdc1-104">Образец состоит из следующих проектов.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="6fdc1-105">**Service**</span><span class="sxs-lookup"><span data-stu-id="6fdc1-105">**Service**</span></span>

<span data-ttu-id="6fdc1-106">Это автономная служба WCF, которая реализует интерфейс `ICalculator` и защищает конечную точку с помощью <xref:System.ServiceModel.WSHttpBinding> с защищенным сеансом и отключением надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="6fdc1-107">Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="6fdc1-108">**Клиент**</span><span class="sxs-lookup"><span data-stu-id="6fdc1-108">**Client**</span></span>

<span data-ttu-id="6fdc1-109">Это клиент WCF, который обращается к службе после успешной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="6fdc1-110">Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="6fdc1-111">Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="6fdc1-112">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="6fdc1-112">To use this sample</span></span>

1. <span data-ttu-id="6fdc1-113">Откройте решение Криптоагилити. sln в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="6fdc1-114">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="6fdc1-115">Откройте проводник и перейдите в каталог \Вкф\басик\секурити\криптоагилити\сервице\бин и запустите файл Service. exe с правами администратора, щелкнув правой кнопкой мыши Service. exe и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-115">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="6fdc1-116">Перейдите в каталог \WCF\Basic\Security\CryptoAgility\Client\bin и запустите файл client.exe обычным образом.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fdc1-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6fdc1-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6fdc1-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6fdc1-119">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6fdc1-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6fdc1-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="6fdc1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6fdc1-121">See also</span></span>

- [<span data-ttu-id="6fdc1-122">Безопасность Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="6fdc1-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
