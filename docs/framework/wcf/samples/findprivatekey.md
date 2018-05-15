---
title: Образец FindPrivateKey - WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 72e2f49ae7c39b4a0486ec053ff1164c2d833cbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="46bbd-102">Образец FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="46bbd-102">FindPrivateKey sample</span></span>

<span data-ttu-id="46bbd-103">Определение расположения и имени файла закрытого ключа, связанного с заданным сертификатом X.509, в хранилище сертификатов может представлять собой достаточно сложную задачу.</span><span class="sxs-lookup"><span data-stu-id="46bbd-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="46bbd-104">Средство FindPrivateKey.exe упрощает этот процесс.</span><span class="sxs-lookup"><span data-stu-id="46bbd-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46bbd-105">FindPrivateKey - это образец, который необходимо скомпилировать перед началом использования.</span><span class="sxs-lookup"><span data-stu-id="46bbd-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="46bbd-106">В разделе [построение проекта FindPrivateKey](#to-build-the-findprivatekey-project) разделе инструкции по созданию средство FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="46bbd-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="46bbd-107">Сертификаты X.509 устанавливаются администратором или любым пользователем компьютера.</span><span class="sxs-lookup"><span data-stu-id="46bbd-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="46bbd-108">Однако сертификат может обращаться служба, выполняющаяся с другой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="46bbd-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="46bbd-109">Например учетную запись СЕТЕВОЙ службы.</span><span class="sxs-lookup"><span data-stu-id="46bbd-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="46bbd-110">У такой учетной записи может не быть доступа к файлу закрытого ключа, поскольку изначально сертификат был установлен другой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="46bbd-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="46bbd-111">Средство FindPrivateKey позволяет определить расположение файла закрытого ключа заданного сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="46bbd-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="46bbd-112">Если расположение файла закрытого ключа заданного сертификата X.509 известно, можно добавлять или удалять разрешения на доступ к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="46bbd-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="46bbd-113">Образцы, которые используют сертификаты для безопасности с помощью средства FindPrivateKey в *Setup.bat* файла.</span><span class="sxs-lookup"><span data-stu-id="46bbd-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="46bbd-114">Когда файл закрытого ключа будет найден, можно использовать другие средства, например *Cacls.exe* для установки соответствующих прав доступа в файле.</span><span class="sxs-lookup"><span data-stu-id="46bbd-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="46bbd-115">При запуске службы Windows Communication Foundation (WCF) учетной записи пользователя, например резидентно размещенного исполняемого файла, убедитесь, что учетная запись пользователя имеет доступ только для чтения к файлу.</span><span class="sxs-lookup"><span data-stu-id="46bbd-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="46bbd-116">При запуске службы WCF в Internet Information Services (IIS) учетные записи по умолчанию, которые служба будет выполняться, NETWORK SERVICE в службах IIS 7 и более ранних версий, или удостоверение пула приложений IIS 7.5 и более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="46bbd-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="46bbd-117">Дополнительные сведения см. в разделе [удостоверений пула приложений](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="46bbd-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="46bbd-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="46bbd-118">Examples</span></span>

<span data-ttu-id="46bbd-119">При доступе к сертификата, для которого у процесса нет права на чтения, появится сообщение об исключении примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="46bbd-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="46bbd-120">В этом случае с помощью средства FindPrivateKey найти файл закрытого ключа и затем задайте права доступа для процесса, в которой запущена служба.</span><span class="sxs-lookup"><span data-stu-id="46bbd-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="46bbd-121">Например это можно сделать с помощью средства Cacls.exe, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="46bbd-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="46bbd-122">Построение проекта FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="46bbd-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="46bbd-123">Чтобы загрузить проект, посетите [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="46bbd-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="46bbd-124">Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и перейдите к *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* папки в каталоге, где установлен образец.</span><span class="sxs-lookup"><span data-stu-id="46bbd-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="46bbd-125">Дважды щелкните значок файла с расширением SLN, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46bbd-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="46bbd-126">В **построения** последовательно выберите пункты **Перестроить решение**.</span><span class="sxs-lookup"><span data-stu-id="46bbd-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="46bbd-127">В результате построения решения будет создан файл FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="46bbd-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="46bbd-128">Соглашения-записи командной строки</span><span class="sxs-lookup"><span data-stu-id="46bbd-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="46bbd-129">«[*параметр*]» представляет набор необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="46bbd-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="46bbd-130">«{*параметр*}» представляет набор обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="46bbd-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="46bbd-131">«*параметр1* &#124; *параметр2*» представляет выбор между наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="46bbd-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="46bbd-132">«\<*значение*>» представляет значение параметра ввода.</span><span class="sxs-lookup"><span data-stu-id="46bbd-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="46bbd-133">Использование</span><span class="sxs-lookup"><span data-stu-id="46bbd-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="46bbd-134">Где:</span><span class="sxs-lookup"><span data-stu-id="46bbd-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="46bbd-135">Если параметры не указаны в командной строке, отображается этот текст справки.</span><span class="sxs-lookup"><span data-stu-id="46bbd-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="46bbd-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="46bbd-136">Examples</span></span>

<span data-ttu-id="46bbd-137">Этот пример находит имя файла сертификата с именем субъекта «CN = localhost», в личном хранилище текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="46bbd-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="46bbd-138">Этот пример находит имя файла сертификата с именем субъекта «CN = localhost», в личное хранилище текущего пользователя и выводит полный путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="46bbd-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="46bbd-139">Этот пример находит имя файла сертификата с отпечатком "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" в хранилище "Личное" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="46bbd-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
