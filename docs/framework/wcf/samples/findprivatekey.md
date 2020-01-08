---
title: Пример FindPrivateKey
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346016"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="301bb-102">Пример FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="301bb-102">FindPrivateKey sample</span></span>

<span data-ttu-id="301bb-103">Определение расположения и имени файла закрытого ключа, связанного с заданным сертификатом X.509, в хранилище сертификатов может представлять собой достаточно сложную задачу.</span><span class="sxs-lookup"><span data-stu-id="301bb-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="301bb-104">Средство FindPrivateKey.exe упрощает этот процесс.</span><span class="sxs-lookup"><span data-stu-id="301bb-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="301bb-105">FindPrivateKey - это образец, который необходимо скомпилировать перед началом использования.</span><span class="sxs-lookup"><span data-stu-id="301bb-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="301bb-106">Инструкции по созданию средства FindPrivateKey см. в разделе [To Build The FindPrivateKey Project](#to-build-the-findprivatekey-project) .</span><span class="sxs-lookup"><span data-stu-id="301bb-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="301bb-107">Сертификаты X.509 устанавливаются администратором или любым пользователем компьютера.</span><span class="sxs-lookup"><span data-stu-id="301bb-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="301bb-108">Тем не менее, доступ к сертификату может осуществляться службой, работающей под другой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="301bb-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="301bb-109">Например, учетная запись сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="301bb-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="301bb-110">У такой учетной записи может не быть доступа к файлу закрытого ключа, поскольку изначально сертификат был установлен другой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="301bb-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="301bb-111">Средство FindPrivateKey позволяет определить расположение файла закрытого ключа заданного сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="301bb-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="301bb-112">Если расположение файла закрытого ключа заданного сертификата X.509 известно, можно добавлять или удалять разрешения на доступ к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="301bb-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="301bb-113">Примеры, использующие сертификаты для обеспечения безопасности, используют средство FindPrivateKey в файле *Setup. bat* .</span><span class="sxs-lookup"><span data-stu-id="301bb-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="301bb-114">После того как файл закрытого ключа будет найден, можно использовать другие средства, такие как *cacls. exe* , для установки соответствующих прав доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="301bb-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="301bb-115">При запуске службы Windows Communication Foundation (WCF) под учетной записью пользователя, такой как исполняемый файл с автономным размещением, убедитесь, что учетная запись пользователя имеет доступ только для чтения к файлу.</span><span class="sxs-lookup"><span data-stu-id="301bb-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="301bb-116">При запуске службы WCF в службы IIS (IIS) учетные записи по умолчанию, под которыми работает служба, — это СЕТЕВая служба в IIS 7 и более ранних версиях или удостоверение пула приложений в IIS 7,5 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="301bb-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="301bb-117">Дополнительные сведения см. в разделе [удостоверения пула приложений](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="301bb-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="301bb-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="301bb-118">Examples</span></span>

<span data-ttu-id="301bb-119">При доступе к сертификату, для которого у процесса нет прав на чтение, отображается сообщение об исключении, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="301bb-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="301bb-120">В этом случае используйте средство FindPrivateKey, чтобы найти файл закрытого ключа, а затем установите право доступа для процесса, от имени которого запущена служба.</span><span class="sxs-lookup"><span data-stu-id="301bb-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="301bb-121">Например, это можно сделать с помощью средства cacls. exe, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="301bb-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="301bb-122">Построение проекта FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="301bb-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="301bb-123">Чтобы скачать проект, перейдите на страницу [примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="301bb-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="301bb-124">Откройте проводник и перейдите в папку *WF_WCF_Samples \вкф\сетуп\финдприватекэй\кс* в каталоге, где был установлен пример.</span><span class="sxs-lookup"><span data-stu-id="301bb-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="301bb-125">Дважды щелкните значок файла с расширением SLN, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="301bb-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="301bb-126">В меню **Сборка** выберите **Перестроить решение**.</span><span class="sxs-lookup"><span data-stu-id="301bb-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="301bb-127">В результате построения решения будет создан файл FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="301bb-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="301bb-128">Соглашения — записи командной строки</span><span class="sxs-lookup"><span data-stu-id="301bb-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="301bb-129">"[*параметр*]" представляет необязательный набор параметров.</span><span class="sxs-lookup"><span data-stu-id="301bb-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="301bb-130">"{*Option*}" представляет обязательный набор параметров.</span><span class="sxs-lookup"><span data-stu-id="301bb-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="301bb-131">"*параметр1* &#124; *параметр2*" представляет выбор между наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="301bb-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="301bb-132">"\<*значение*>" представляет значение параметра, которое необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="301bb-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="301bb-133">Метрики</span><span class="sxs-lookup"><span data-stu-id="301bb-133">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="301bb-134">Где:</span><span class="sxs-lookup"><span data-stu-id="301bb-134">Where:</span></span>

| <span data-ttu-id="301bb-135">Параметр</span><span class="sxs-lookup"><span data-stu-id="301bb-135">Parameter</span></span>         | <span data-ttu-id="301bb-136">Описание</span><span class="sxs-lookup"><span data-stu-id="301bb-136">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="301bb-137">Имя субъекта сертификата</span><span class="sxs-lookup"><span data-stu-id="301bb-137">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="301bb-138">Отпечаток сертификата (для поиска можно использовать средство certmgr. exe)</span><span class="sxs-lookup"><span data-stu-id="301bb-138">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="301bb-139">только имя выходного файла</span><span class="sxs-lookup"><span data-stu-id="301bb-139">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="301bb-140">только выходной каталог</span><span class="sxs-lookup"><span data-stu-id="301bb-140">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="301bb-141">абсолютное имя выходного файла</span><span class="sxs-lookup"><span data-stu-id="301bb-141">output absolute file name</span></span>                                                         |

<span data-ttu-id="301bb-142">Если в командной строке не указаны параметры, отображается текст справки с этими сведениями.</span><span class="sxs-lookup"><span data-stu-id="301bb-142">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="301bb-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="301bb-143">Examples</span></span>

<span data-ttu-id="301bb-144">В этом примере выполняется поиск имени файла сертификата с именем субъекта "CN = localhost" в личном хранилище текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="301bb-144">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="301bb-145">В этом примере выполняется поиск имени файла сертификата с именем субъекта "CN = localhost" в личном хранилище текущего пользователя и вывод полного пути к каталогу.</span><span class="sxs-lookup"><span data-stu-id="301bb-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="301bb-146">Этот пример находит имя файла сертификата с отпечатком "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" в хранилище "Личное" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="301bb-146">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
