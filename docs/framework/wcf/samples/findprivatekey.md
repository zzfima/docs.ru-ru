---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ca357ccdcbe76f36f3ba56caf2013a80143728
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="f60db-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="f60db-102">FindPrivateKey</span></span>
<span data-ttu-id="f60db-103">Определение расположения и имени файла закрытого ключа, связанного с заданным сертификатом X.509, в хранилище сертификатов может представлять собой достаточно сложную задачу.</span><span class="sxs-lookup"><span data-stu-id="f60db-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="f60db-104">Средство FindPrivateKey.exe упрощает этот процесс.</span><span class="sxs-lookup"><span data-stu-id="f60db-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f60db-105">FindPrivateKey - это образец, который необходимо скомпилировать перед началом использования.</span><span class="sxs-lookup"><span data-stu-id="f60db-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="f60db-106">В разделе «Создание проекта FindPrivateKey» ниже инструкции о том, как построить инструмент FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="f60db-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="f60db-107">Сертификаты X.509 устанавливаются администратором или любым пользователем компьютера.</span><span class="sxs-lookup"><span data-stu-id="f60db-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="f60db-108">Однако к сертификату может обращаться служба, выполняющаяся от имени другой учетной записи (например, ASPNET в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или NETWORK SERVICE в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="f60db-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="f60db-109">У такой учетной записи может не быть доступа к файлу закрытого ключа, поскольку изначально сертификат был установлен другой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="f60db-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="f60db-110">Средство FindPrivateKey позволяет определить расположение файла закрытого ключа заданного сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="f60db-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="f60db-111">Если расположение файла закрытого ключа заданного сертификата X.509 известно, можно добавлять или удалять разрешения на доступ к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="f60db-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="f60db-112">В примерах, безопасность которых обеспечивается с помощью сертификатов, средство FindPrivateKey запускается через файл Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="f60db-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="f60db-113">Когда файл закрытого ключа будет найден, можно с помощью других средств (например, Cacls.exe) установить для него соответствующие права доступа.</span><span class="sxs-lookup"><span data-stu-id="f60db-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="f60db-114">При выполнении службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], например резидентно размещенного исполняемого файла, от имени учетной записи пользователя необходимо проверить, что у пользователя есть доступ только для чтения к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="f60db-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="f60db-115">При выполнении службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службах IIS по умолчанию служба выполняется от имени учетной записи ASPNET в [!INCLUDE[wxp](../../../../includes/wxp-md.md)] или NETWORK SERVICE в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], у которых по умолчанию нет доступа к файлу закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="f60db-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f60db-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="f60db-116">Examples</span></span>  
 <span data-ttu-id="f60db-117">При обращении к сертификатам из процесса, у которого нет права на чтения этих сертификатов, появляется сообщение об исключении примерно следующего вида.</span><span class="sxs-lookup"><span data-stu-id="f60db-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="f60db-118">Если это происходит, необходимо с помощью средства FindPrivateKey найти файл закрытого ключа и предоставить доступ к нему для процесса, в котором выполняется служба.</span><span class="sxs-lookup"><span data-stu-id="f60db-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="f60db-119">Например, это можно сделать с помощью средства Cacls.exe, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f60db-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="f60db-120">Построение проекта FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="f60db-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="f60db-121">Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и перейдите к языковому подкаталогу в каталоге, где установлен пример.</span><span class="sxs-lookup"><span data-stu-id="f60db-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="f60db-122">Дважды щелкните значок файла с расширением SLN, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f60db-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="f60db-123">В **построения** последовательно выберите пункты **Перестроить решение**.</span><span class="sxs-lookup"><span data-stu-id="f60db-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="f60db-124">Файлы построения клиентской программы сохраняются в папке client\bin, а файлы построения служебной программы - в папке service\bin.</span><span class="sxs-lookup"><span data-stu-id="f60db-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="f60db-125">В результате построения решения будет создан файл FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="f60db-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="f60db-126">Соглашения - записи командной строки</span><span class="sxs-lookup"><span data-stu-id="f60db-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="f60db-127">«[*параметр*]» представляет набор необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="f60db-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="f60db-128">«{*параметр*}» представляет набор обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="f60db-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="f60db-129">«*параметр1* &#124; *параметр2*«представляет выбор между наборами параметров.</span><span class="sxs-lookup"><span data-stu-id="f60db-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="f60db-130">«\<*значение*>» представляет значение параметра ввода.</span><span class="sxs-lookup"><span data-stu-id="f60db-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f60db-131">Использование</span><span class="sxs-lookup"><span data-stu-id="f60db-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="f60db-132">Где:</span><span class="sxs-lookup"><span data-stu-id="f60db-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="f60db-133">Если в командной строке не указать ни один параметр, появится этот справочный текст.</span><span class="sxs-lookup"><span data-stu-id="f60db-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f60db-134">Примеры</span><span class="sxs-lookup"><span data-stu-id="f60db-134">Examples</span></span>  
 <span data-ttu-id="f60db-135">Этот пример находит имя файла сертификата с именем субъекта "CN=localhost" в хранилище "Личное" текущего пользователя. FindPrivateKey My CurrentUser -n "CN=localhost".</span><span class="sxs-lookup"><span data-stu-id="f60db-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="f60db-136">Этот пример находит имя файла сертификата с именем субъекта "CN=localhost" в хранилище "Личное" текущего пользователя и выводит полный путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="f60db-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="f60db-137">Этот пример находит имя файла сертификата с отпечатком "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" в хранилище "Личное" на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f60db-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="f60db-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f60db-138">See Also</span></span>
