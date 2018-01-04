---
title: "Практическое руководство. Установка и настройка компонентов активации WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78c63fe58872097058292a8b100b376959a2a0b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="4b0b0-102">Практическое руководство. Установка и настройка компонентов активации WCF</span><span class="sxs-lookup"><span data-stu-id="4b0b0-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="4b0b0-103">В этом разделе описывается настройка службы активации Windows (WAS) в [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], обменивающихся данными не по сетевым протоколам HTTP.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="4b0b0-104">Настройка предполагает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-104">The following sections outline the steps for this configuration:</span></span>  
  
-   <span data-ttu-id="4b0b0-105">Установите или проверьте, установлены ли компоненты активации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b0b0-105">Install (or confirm the installation of) the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activation components.</span></span>  
  
-   <span data-ttu-id="4b0b0-106">Настройте WAS на поддержку отличных от HTTP протоколов.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="4b0b0-107">Выполнение описанных ниже действий позволяет настроить [!INCLUDE[wv](../../../../includes/wv-md.md)] для активации TCP.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="4b0b0-108">После установки и настройки WAS, в разделе [как: размещение службы WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) для процедуры создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы, предоставляющей конечную точку отличные от HTTP, которая использует WAS.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="4b0b0-109">Установка компонентов активации WCF, работающих по отличному от HTTP протоколу</span><span class="sxs-lookup"><span data-stu-id="4b0b0-109">To install the WCF non-HTTP activation components</span></span>  
  
1.  <span data-ttu-id="4b0b0-110">Нажмите кнопку **запустить** , а затем нажмите **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="4b0b0-111">Нажмите кнопку **программы**, а затем нажмите кнопку **программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="4b0b0-112">На **задачи** меню, нажмите кнопку **Включение или отключение компонентов**.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4.  <span data-ttu-id="4b0b0-113">Найдите узел [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], затем выберите и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-113">Find the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] node, select and then expand it.</span></span>  
  
5.  <span data-ttu-id="4b0b0-114">Выберите **компоненты активации WCF не-Http** и сохраните параметр.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="4b0b0-115">Настройка WAS на поддержку протокола TCP</span><span class="sxs-lookup"><span data-stu-id="4b0b0-115">To configure the WAS to support TCP activation</span></span>  
  
1.  <span data-ttu-id="4b0b0-116">Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="4b0b0-117">Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b0b0-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="4b0b0-118">В окне командной строки с правами администратора выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4b0b0-119">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-119">This command is a single line of text.</span></span> <span data-ttu-id="4b0b0-120">Она добавляет привязку узла к протоколу net.tcp в веб-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2.  <span data-ttu-id="4b0b0-121">Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="4b0b0-122">Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4b0b0-123">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-123">This command is a single line of text.</span></span> <span data-ttu-id="4b0b0-124">Эта команда включает /\<*приложения WCF*> приложение было доступно с помощью обоих http://localhost*/\<приложения WCF >* и net.tcp:// localhost /*\<приложения WCF >*.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-124">This command enables the /\<*WCF Application*> application to be accessed using both http://localhost*/\<WCF Application>* and net.tcp://localhost/*\<WCF Application>*.</span></span>  
  
     <span data-ttu-id="4b0b0-125">Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="4b0b0-126">Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="4b0b0-127">Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="4b0b0-128">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-128">This command is a single line of text.</span></span>  
  
    2.  <span data-ttu-id="4b0b0-129">Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="4b0b0-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="4b0b0-130">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="4b0b0-131">Удаление протокола net.tcp из списка разрешенных протоколов</span><span class="sxs-lookup"><span data-stu-id="4b0b0-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1.  <span data-ttu-id="4b0b0-132">Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4b0b0-133">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="4b0b0-134">Удаление привязки узла к протоколу net.tcp</span><span class="sxs-lookup"><span data-stu-id="4b0b0-134">To remove the net.tcp site binding</span></span>  
  
1.  <span data-ttu-id="4b0b0-135">Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="4b0b0-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4b0b0-136">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="4b0b0-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0b0-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4b0b0-137">See Also</span></span>  
 [<span data-ttu-id="4b0b0-138">Активация TCP</span><span class="sxs-lookup"><span data-stu-id="4b0b0-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [<span data-ttu-id="4b0b0-139">Активация MSMQ</span><span class="sxs-lookup"><span data-stu-id="4b0b0-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [<span data-ttu-id="4b0b0-140">Активация NamedPipe</span><span class="sxs-lookup"><span data-stu-id="4b0b0-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [<span data-ttu-id="4b0b0-141">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="4b0b0-141">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
