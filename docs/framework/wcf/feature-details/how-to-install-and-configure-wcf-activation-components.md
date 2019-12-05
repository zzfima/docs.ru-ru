---
title: Практическое руководство. Установка и настройка компонентов активации WCF
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 0a7be97ec157638db3eb2d656fe263b37b8d676c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837419"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="efb0a-102">Практическое руководство. Установка и настройка компонентов активации WCF</span><span class="sxs-lookup"><span data-stu-id="efb0a-102">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="efb0a-103">В этом разделе описываются шаги, необходимые для настройки службы активации Windows (также известной как WAS) в Windows Vista для размещения служб Windows Communication Foundation (WCF), не передающих сетевые протоколы HTTP.</span><span class="sxs-lookup"><span data-stu-id="efb0a-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="efb0a-104">Настройка предполагает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="efb0a-104">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="efb0a-105">Установите (или подтвердите установку) компоненты активации WCF.</span><span class="sxs-lookup"><span data-stu-id="efb0a-105">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="efb0a-106">Настройте WAS на поддержку отличных от HTTP протоколов.</span><span class="sxs-lookup"><span data-stu-id="efb0a-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="efb0a-107">Следующая процедура настраивает Windows Vista для активации TCP.</span><span class="sxs-lookup"><span data-stu-id="efb0a-107">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="efb0a-108">После установки и настройки WAS см. раздел [как разместить службу WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) для процедур создания службы WCF, предоставляющей конечную точку, которая не является КОНЕЧНОЙ точкой HTTP.</span><span class="sxs-lookup"><span data-stu-id="efb0a-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="efb0a-109">Установка компонентов активации WCF, работающих по отличному от HTTP протоколу</span><span class="sxs-lookup"><span data-stu-id="efb0a-109">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="efb0a-110">Нажмите кнопку " **Пуск** " и выберите **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="efb0a-110">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="efb0a-111">Последовательно выберите **Программы**, **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="efb0a-111">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="efb0a-112">В меню **задачи** выберите команду **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="efb0a-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="efb0a-113">Найдите узел WinFX, выберите и разверните его.</span><span class="sxs-lookup"><span data-stu-id="efb0a-113">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="efb0a-114">Выберите пункт **WCF-компоненты активации, отличные от HTTP** и сохраните параметр.</span><span class="sxs-lookup"><span data-stu-id="efb0a-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="efb0a-115">Настройка WAS на поддержку протокола TCP</span><span class="sxs-lookup"><span data-stu-id="efb0a-115">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="efb0a-116">Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp.</span><span class="sxs-lookup"><span data-stu-id="efb0a-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="efb0a-117">Это можно сделать с помощью Appcmd. exe, который устанавливается вместе с набором средств управления IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="efb0a-117">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="efb0a-118">В окне командной строки с правами администратора выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="efb0a-118">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="efb0a-119">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-119">This command is a single line of text.</span></span> <span data-ttu-id="efb0a-120">Она добавляет привязку узла к протоколу net.tcp в веб-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.</span><span class="sxs-lookup"><span data-stu-id="efb0a-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="efb0a-121">Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно.</span><span class="sxs-lookup"><span data-stu-id="efb0a-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="efb0a-122">Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="efb0a-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="efb0a-123">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-123">This command is a single line of text.</span></span> <span data-ttu-id="efb0a-124">Эта команда позволяет получить доступ к приложению\<*WCF*>, используя как `http://localhost/<WCF Application>`, так и `net.tcp://localhost/<WCF Application>`.</span><span class="sxs-lookup"><span data-stu-id="efb0a-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="efb0a-125">Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.</span><span class="sxs-lookup"><span data-stu-id="efb0a-125">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="efb0a-126">Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.</span><span class="sxs-lookup"><span data-stu-id="efb0a-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="efb0a-127">Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="efb0a-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="efb0a-128">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-128">This command is a single line of text.</span></span>

    2. <span data-ttu-id="efb0a-129">Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="efb0a-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="efb0a-130">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-130">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="efb0a-131">Удаление протокола net.tcp из списка разрешенных протоколов</span><span class="sxs-lookup"><span data-stu-id="efb0a-131">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="efb0a-132">Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="efb0a-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="efb0a-133">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-133">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="efb0a-134">Удаление привязки узла к протоколу net.tcp</span><span class="sxs-lookup"><span data-stu-id="efb0a-134">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="efb0a-135">Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="efb0a-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="efb0a-136">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="efb0a-136">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="efb0a-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="efb0a-137">See also</span></span>

- [<span data-ttu-id="efb0a-138">Активация TCP</span><span class="sxs-lookup"><span data-stu-id="efb0a-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="efb0a-139">Активация MSMQ</span><span class="sxs-lookup"><span data-stu-id="efb0a-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="efb0a-140">Активация NamedPipe</span><span class="sxs-lookup"><span data-stu-id="efb0a-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="efb0a-141">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="efb0a-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
