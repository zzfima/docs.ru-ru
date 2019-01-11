---
title: Инструкции по установке сертификата сервера в службах IIS
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: a89d907b9be25c83a74f0c5d60d184637552f297
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221106"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="25663-102">Инструкции по установке сертификата сервера в службах IIS</span><span class="sxs-lookup"><span data-stu-id="25663-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="25663-103">Чтобы запускать примеры, которые безопасным образом взаимодействуют со службами IIS, необходимо создать и установить сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="25663-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="25663-104">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="25663-104">Step 1.</span></span> <span data-ttu-id="25663-105">Создание сертификатов</span><span class="sxs-lookup"><span data-stu-id="25663-105">Creating Certificates</span></span>  
 <span data-ttu-id="25663-106">Чтобы создать сертификат для компьютера, откройте командную строку разработчика для Visual Studio с правами администратора и запустите файл Setup.bat, входящий в состав каждого из образцов, которые используют безопасное взаимодействие со службами IIS.</span><span class="sxs-lookup"><span data-stu-id="25663-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="25663-107">Перед запуском пакетного файла убедитесь, что путь включает папку, содержащую программу Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="25663-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="25663-108">Следующая команда служит для создания сертификата в файле Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="25663-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="25663-109">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="25663-109">Step 2.</span></span> <span data-ttu-id="25663-110">Установка сертификатов</span><span class="sxs-lookup"><span data-stu-id="25663-110">Installing Certificates</span></span>  
 <span data-ttu-id="25663-111">Шаги, необходимые для установки созданных сертификатов, зависят от используемой версии IIS.</span><span class="sxs-lookup"><span data-stu-id="25663-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="25663-112">Установка IIS в IIS 5.1 (Windows XP) и IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="25663-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1.  <span data-ttu-id="25663-113">Откройте оснастку консоли MMC диспетчера служб IIS.</span><span class="sxs-lookup"><span data-stu-id="25663-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2.  <span data-ttu-id="25663-114">Щелкните правой кнопкой мыши веб-сайта по умолчанию и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="25663-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="25663-115">Выберите **Безопасность каталога** вкладки.</span><span class="sxs-lookup"><span data-stu-id="25663-115">Select the **Directory Security** tab.</span></span>  
  
4.  <span data-ttu-id="25663-116">Нажмите кнопку **сертификат сервера** кнопки.</span><span class="sxs-lookup"><span data-stu-id="25663-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="25663-117">Будет запущен мастер сертификатов веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="25663-117">The Web Server Certificate Wizard starts.</span></span>  
  
5.  <span data-ttu-id="25663-118">Завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="25663-118">Complete the wizard.</span></span> <span data-ttu-id="25663-119">Выберите назначение сертификата.</span><span class="sxs-lookup"><span data-stu-id="25663-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="25663-120">Из отображаемого списка сертификатов выберите сертификат ServiceModelSamples-HTTPS-Server.</span><span class="sxs-lookup"><span data-stu-id="25663-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="25663-121">![Мастер сертификатов IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="25663-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6.  <span data-ttu-id="25663-122">Тестирование доступа к службе в браузере с помощью HTTPS-адрес `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="25663-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="25663-123">Если до этого был настроен протокол SSL с помощью Httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="25663-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1.  <span data-ttu-id="25663-124">С помощью программы Makecert.exe (или запустив файл Setup.bat) создайте сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="25663-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2.  <span data-ttu-id="25663-125">Запустите диспетчер IIS и установите сертификат в соответствии с описанными выше действиями.</span><span class="sxs-lookup"><span data-stu-id="25663-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3.  <span data-ttu-id="25663-126">Добавьте следующую строку кода в клиентскую программу.</span><span class="sxs-lookup"><span data-stu-id="25663-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="25663-127">Этот код необходим только для тестовых сертификатов, наподобие созданных с помощью Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="25663-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="25663-128">Для кода производственного назначения это делать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="25663-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="25663-129">Установка IIS в IIS 7.0 (Windows Vista и Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="25663-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1.  <span data-ttu-id="25663-130">Из **запустить** меню, нажмите кнопку **запуска**, затем введите **inetmgr** чтобы открыть оснастку MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="25663-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="25663-131">Щелкните правой кнопкой мыши **Default Web Site** и выберите **изменить привязки...**</span><span class="sxs-lookup"><span data-stu-id="25663-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3.  <span data-ttu-id="25663-132">Нажмите кнопку **добавить** кнопки **привязки сайта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="25663-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4.  <span data-ttu-id="25663-133">Выберите **HTTPS** из **тип** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="25663-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5.  <span data-ttu-id="25663-134">Выберите **ServiceModelSamples-HTTPS-Server** из **SSL-сертификат** стрелку раскрывающегося списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="25663-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6.  <span data-ttu-id="25663-135">Тестирование доступа к службе в браузере с помощью HTTPS-адрес `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="25663-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25663-136">Поскольку только что установленный тестовый сертификат не является доверенным сертификатом, при переходе по локальным веб-адресам, защищенным с помощью этого сертификата, могут появиться дополнительные предупреждения системы безопасности Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="25663-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="25663-137">Удаление сертификатов</span><span class="sxs-lookup"><span data-stu-id="25663-137">Removing Certificates</span></span>  
  
-   <span data-ttu-id="25663-138">Выполните с помощью диспетчера служб IIS действия, описанные выше, но вместо добавления сертификата или привязки удалите их.</span><span class="sxs-lookup"><span data-stu-id="25663-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
-   <span data-ttu-id="25663-139">Удалите сертификат компьютера с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="25663-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
