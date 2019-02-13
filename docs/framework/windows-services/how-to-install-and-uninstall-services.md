---
title: Как выполнить  Установка и удаление служб Windows
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 43b5ad2f346406897e8bcbcce5660a6c9524f9af
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826277"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="43aa1-102">Как выполнить  Установка и удаление служб Windows</span><span class="sxs-lookup"><span data-stu-id="43aa1-102">How to: Install and uninstall Windows services</span></span>
<span data-ttu-id="43aa1-103">Если вы разрабатываете службу Windows с помощью платформы .NET Framework, можно быстро установить приложение службы с помощью служебной программы командной строки [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md).</span><span class="sxs-lookup"><span data-stu-id="43aa1-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility.</span></span> <span data-ttu-id="43aa1-104">Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield.</span><span class="sxs-lookup"><span data-stu-id="43aa1-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="43aa1-105">Дополнительные сведения см. в разделе [Создание пакета установщика (клиент Windows)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span><span class="sxs-lookup"><span data-stu-id="43aa1-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>
  
> [!WARNING]
>  <span data-ttu-id="43aa1-106">Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье.</span><span class="sxs-lookup"><span data-stu-id="43aa1-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="43aa1-107">Вместо этого определите, какая программа (или программный пакет) установила эту службу, а затем выберите **Приложения** в параметрах, чтобы удалить эту программу.</span><span class="sxs-lookup"><span data-stu-id="43aa1-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="43aa1-108">Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.</span><span class="sxs-lookup"><span data-stu-id="43aa1-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="43aa1-109">Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows.</span><span class="sxs-lookup"><span data-stu-id="43aa1-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="43aa1-110">Дополнительные сведения см. в разделе [Пошаговое руководство: создание диспетчера служб Windows](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="43aa1-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="43aa1-111">Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="43aa1-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="43aa1-112">Перед запуском проекта необходимо установить службу в проекте.</span><span class="sxs-lookup"><span data-stu-id="43aa1-112">Before you can run the project, you must install the service in the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="43aa1-113">Запустите **обозреватель сервера** и убедитесь, что служба установлена или удалена.</span><span class="sxs-lookup"><span data-stu-id="43aa1-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="43aa1-114">Дополнительные сведения см. в разделе [Практическое руководство. Использование обозревателя сервера в Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="43aa1-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>
  
### <a name="install-your-service-manually"></a><span data-ttu-id="43aa1-115">Установка службы вручную</span><span class="sxs-lookup"><span data-stu-id="43aa1-115">Install your service manually</span></span>  
  
1.  <span data-ttu-id="43aa1-116">В меню **Пуск** выберите каталог **Visual Studio \<*версия*>**, а затем выберите **Командная строка разработчика для VS \<*версия*>**.</span><span class="sxs-lookup"><span data-stu-id="43aa1-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="43aa1-117">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43aa1-117">The Developer Command Prompt for Visual Studio appears.</span></span> 
  
2.  <span data-ttu-id="43aa1-118">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="43aa1-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="43aa1-119">Запустите *InstallUtil.exe* из командной строки, указав исполняемый файл проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="43aa1-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     <span data-ttu-id="43aa1-120">Если вы используете командную строку разработчика для Visual Studio, системный путь должен указывать на файл *InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="43aa1-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="43aa1-121">Если это не так, можно добавить его в путь или использовать полный путь для его вызова.</span><span class="sxs-lookup"><span data-stu-id="43aa1-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="43aa1-122">Этот инструмент устанавливается вместе с платформой .NET Framework в папку *%WINDIR%\Microsoft.NET\Framework[64]\\<версия_платформы>*.</span><span class="sxs-lookup"><span data-stu-id="43aa1-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version>*.</span></span>
     
     <span data-ttu-id="43aa1-123">Например:</span><span class="sxs-lookup"><span data-stu-id="43aa1-123">For example:</span></span>
     - <span data-ttu-id="43aa1-124">Для 32-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: если каталог установки Windows — *C:\Windows*, по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="43aa1-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="43aa1-125">Для 64-разрядной версии .NET Framework 4 или 4.5 и более поздних версий: по умолчанию используется путь *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="43aa1-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>
  
### <a name="uninstall-your-service-manually"></a><span data-ttu-id="43aa1-126">Удаление службы вручную</span><span class="sxs-lookup"><span data-stu-id="43aa1-126">Uninstall your service manually</span></span>  
  
1. <span data-ttu-id="43aa1-127">В меню **Пуск** выберите каталог **Visual Studio \<*версия*>**, а затем выберите **Командная строка разработчика для VS \<*версия*>**.</span><span class="sxs-lookup"><span data-stu-id="43aa1-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="43aa1-128">Появится командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43aa1-128">The Developer Command Prompt for Visual Studio appears.</span></span>  
  
2.  <span data-ttu-id="43aa1-129">Запустите *InstallUtil.exe* из командной строки, указав выходные данные проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="43aa1-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. <span data-ttu-id="43aa1-130">После удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="43aa1-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="43aa1-131">В этом случае удалить запись службы из реестра можно с помощью команды [sc delete](/windows-server/administration/windows-commands/sc-delete).</span><span class="sxs-lookup"><span data-stu-id="43aa1-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43aa1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="43aa1-132">See also</span></span>
- [<span data-ttu-id="43aa1-133">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="43aa1-133">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="43aa1-134">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="43aa1-134">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="43aa1-135">Практическое руководство. Добавление установщиков в приложение-службу</span><span class="sxs-lookup"><span data-stu-id="43aa1-135">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="43aa1-136">Installutil.exe (установщик)</span><span class="sxs-lookup"><span data-stu-id="43aa1-136">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
