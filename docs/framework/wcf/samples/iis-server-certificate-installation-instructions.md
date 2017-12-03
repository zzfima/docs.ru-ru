---
title: "Инструкции по установке сертификата сервера в службах IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d035e703b79eb184bf06e3e75255e2f987c170
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="15367-102">Инструкции по установке сертификата сервера в службах IIS</span><span class="sxs-lookup"><span data-stu-id="15367-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="15367-103">Чтобы запускать примеры, которые безопасным образом взаимодействуют со службами IIS, необходимо создать и установить сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="15367-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="15367-104">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="15367-104">Step 1.</span></span> <span data-ttu-id="15367-105">Создание сертификатов</span><span class="sxs-lookup"><span data-stu-id="15367-105">Creating Certificates</span></span>  
 <span data-ttu-id="15367-106">Чтобы создать сертификат для своего компьютера, откройте командную строку Visual Studio с правами администратора и запустите файл Setup.bat, входящий в состав каждого из образцов, где используется безопасный обмен данными с IIS.</span><span class="sxs-lookup"><span data-stu-id="15367-106">To create a certificate for your computer, open a Visual Studio command prompt with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="15367-107">Перед запуском пакетного файла убедитесь, что путь включает папку, содержащую программу Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="15367-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="15367-108">Следующая команда служит для создания сертификата в файле Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="15367-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="15367-109">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="15367-109">Step 2.</span></span> <span data-ttu-id="15367-110">Установка сертификатов</span><span class="sxs-lookup"><span data-stu-id="15367-110">Installing Certificates</span></span>  
 <span data-ttu-id="15367-111">Шаги, необходимые для установки созданных сертификатов, зависят от используемой версии IIS.</span><span class="sxs-lookup"><span data-stu-id="15367-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="15367-112">Установка IIS в IIS 5.1 (Windows XP) и IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="15367-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1.  <span data-ttu-id="15367-113">Откройте оснастку консоли MMC диспетчера служб IIS.</span><span class="sxs-lookup"><span data-stu-id="15367-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2.  <span data-ttu-id="15367-114">Щелкните правой кнопкой мыши веб-узел по умолчанию и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="15367-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="15367-115">Выберите **Безопасность каталога** вкладки.</span><span class="sxs-lookup"><span data-stu-id="15367-115">Select the **Directory Security** tab.</span></span>  
  
4.  <span data-ttu-id="15367-116">Нажмите кнопку **сертификат сервера** кнопки.</span><span class="sxs-lookup"><span data-stu-id="15367-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="15367-117">Будет запущен мастер сертификатов веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="15367-117">The Web Server Certificate Wizard starts.</span></span>  
  
5.  <span data-ttu-id="15367-118">Выполните указания мастера.</span><span class="sxs-lookup"><span data-stu-id="15367-118">Complete the wizard.</span></span> <span data-ttu-id="15367-119">Выберите назначение сертификата.</span><span class="sxs-lookup"><span data-stu-id="15367-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="15367-120">Из отображаемого списка сертификатов выберите сертификат ServiceModelSamples-HTTPS-Server.</span><span class="sxs-lookup"><span data-stu-id="15367-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="15367-121">![Мастер сертификатов IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="15367-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6.  <span data-ttu-id="15367-122">Протестируйте доступ к службе в браузере, воспользовавшись HTTPS-адресом https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="15367-122">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="15367-123">Если до этого был настроен протокол SSL с помощью Httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="15367-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1.  <span data-ttu-id="15367-124">С помощью программы Makecert.exe (или запустив файл Setup.bat) создайте сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="15367-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2.  <span data-ttu-id="15367-125">Запустите диспетчер IIS и установите сертификат в соответствии с описанными выше действиями.</span><span class="sxs-lookup"><span data-stu-id="15367-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3.  <span data-ttu-id="15367-126">Добавьте следующую строку кода в клиентскую программу.</span><span class="sxs-lookup"><span data-stu-id="15367-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15367-127">Этот код необходим только для тестовых сертификатов, наподобие созданных с помощью Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="15367-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="15367-128">Для кода производственного назначения это делать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="15367-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="15367-129">Установка IIS в IIS 7.0 (Windows Vista и Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="15367-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1.  <span data-ttu-id="15367-130">Из **запустить** меню, нажмите кнопку **запуска**, затем введите **inetmgr** чтобы открыть оснастку MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="15367-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="15367-131">Щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **изменить привязки...**</span><span class="sxs-lookup"><span data-stu-id="15367-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3.  <span data-ttu-id="15367-132">Нажмите кнопку **добавить** кнопки **привязки сайта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="15367-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4.  <span data-ttu-id="15367-133">Выберите **HTTPS** из **тип** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="15367-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5.  <span data-ttu-id="15367-134">Выберите **ServiceModelSamples-HTTPS-Server** из **SSL-сертификат** раскрывающегося списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15367-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6.  <span data-ttu-id="15367-135">Протестируйте доступ к службе в браузере, воспользовавшись HTTPS-адресом https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="15367-135">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15367-136">Поскольку только что установленный тестовый сертификат не является доверенным сертификатом, при переходе по локальным веб-адресам, защищенным с помощью этого сертификата, могут появиться дополнительные предупреждения системы безопасности Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="15367-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="15367-137">Удаление сертификатов</span><span class="sxs-lookup"><span data-stu-id="15367-137">Removing Certificates</span></span>  
  
-   <span data-ttu-id="15367-138">Выполните с помощью диспетчера служб IIS действия, описанные выше, но вместо добавления сертификата или привязки удалите их.</span><span class="sxs-lookup"><span data-stu-id="15367-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
-   <span data-ttu-id="15367-139">Удалите сертификат компьютера с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="15367-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
