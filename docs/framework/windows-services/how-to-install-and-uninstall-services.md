---
title: Практическое руководство. Установка и удаление служб
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
manager: douge
ms.openlocfilehash: 0d42a37b2e84c310569666771ded38e5feca3608
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="937cb-102">Практическое руководство. Установка и удаление служб</span><span class="sxs-lookup"><span data-stu-id="937cb-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="937cb-103">Если вы разрабатываете службу Windows с помощью платформы .NET Framework, можно быстро установить приложение службы с помощью командной служебной программы InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="937cb-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="937cb-104">Если вы являетесь разработчиком и хотите создать службу Windows, которую пользователи могут устанавливать и удалять, необходимо использовать InstallShield.</span><span class="sxs-lookup"><span data-stu-id="937cb-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="937cb-105">В разделе [развертывания установщика Windows](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span><span class="sxs-lookup"><span data-stu-id="937cb-105">See [Windows Installer Deployment](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="937cb-106">Если вы хотите удалить службу на своем компьютере, не выполняйте процедуру, описанную в этой статье.</span><span class="sxs-lookup"><span data-stu-id="937cb-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="937cb-107">Вместо этого определить, какая программа или программный пакет установила службы и выберите **Установка и удаление программ** панели управления для удаления этой программы.</span><span class="sxs-lookup"><span data-stu-id="937cb-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="937cb-108">Следует отметить, что многие службы являются составной частью ОС Windows. Если их удалить, это может привести к нестабильной работе системы.</span><span class="sxs-lookup"><span data-stu-id="937cb-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="937cb-109">Чтобы использовать процедуру, описанную в этой статье, сначала необходимо добавить установщик службы в свою службу Windows.</span><span class="sxs-lookup"><span data-stu-id="937cb-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="937cb-110">В разделе [Пошаговое руководство: создание Windows службы приложения в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="937cb-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="937cb-111">Проекты служб Windows нельзя запускать непосредственно из среды разработки Visual Studio путем нажатия клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="937cb-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="937cb-112">Это происходит потому, что перед запуском проекта сначала необходимо установить службу в проекте.</span><span class="sxs-lookup"><span data-stu-id="937cb-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="937cb-113">Можно запустить **обозревателя серверов** и убедитесь, что служба установлена или удалена.</span><span class="sxs-lookup"><span data-stu-id="937cb-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="937cb-114">Дополнительные сведения см. в разделе как: подключение и инициализация обозревателя базы данных обозревателя сервера.</span><span class="sxs-lookup"><span data-stu-id="937cb-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="937cb-115">Установка службы вручную</span><span class="sxs-lookup"><span data-stu-id="937cb-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="937cb-116">В ОС Windows **запустить** меню или **запустить** выберите **Visual Studio** , **набора средств Visual Studio**, **разработчика Командной строки**.</span><span class="sxs-lookup"><span data-stu-id="937cb-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="937cb-117">Появляется командная строка Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="937cb-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="937cb-118">Откройте каталог, где находится скомпилированный исполняемый файл вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="937cb-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="937cb-119">Запустите InstallUtil.exe из командной строки, указав исполняемый файл проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="937cb-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="937cb-120">Если вы используете командную строку Visual Studio, путь системы должен указывать на InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="937cb-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="937cb-121">Если нет, можно добавить его в путь или использовать полный путь для его вызова.</span><span class="sxs-lookup"><span data-stu-id="937cb-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="937cb-122">Этот инструмент устанавливается с помощью платформы .NET Framework, и его путь — `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span><span class="sxs-lookup"><span data-stu-id="937cb-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="937cb-123">Например, для 32-разрядной платформы .NET Framework 4 или 4.5. \*, если вашим каталогом установки Windows является C:\Windows, то путь — `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="937cb-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.\*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="937cb-124">Для 64-разрядной версии платформы .NET Framework 4 или 4.5. \*, путь по умолчанию — `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="937cb-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="937cb-125">Удаление службы вручную</span><span class="sxs-lookup"><span data-stu-id="937cb-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="937cb-126">В ОС Windows **запустить** меню или **запустить** выберите **Visual Studio**, **набора средств Visual Studio**, **разработчика Командной строки**.</span><span class="sxs-lookup"><span data-stu-id="937cb-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="937cb-127">Появляется командная строка Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="937cb-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="937cb-128">Запустите InstallUtil.exe из командной строки, указав выходные данные проекта в качестве параметра:</span><span class="sxs-lookup"><span data-stu-id="937cb-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="937cb-129">Иногда после удаления исполняемого файла для службы сама служба может по-прежнему присутствовать в реестре.</span><span class="sxs-lookup"><span data-stu-id="937cb-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="937cb-130">В этом случае команда [sc delete](http://technet.microsoft.com/library/cc742045.aspx) удалить запись для службы из реестра.</span><span class="sxs-lookup"><span data-stu-id="937cb-130">In that case, use the command [sc delete](http://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937cb-131">См. также</span><span class="sxs-lookup"><span data-stu-id="937cb-131">See Also</span></span>  
 [<span data-ttu-id="937cb-132">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="937cb-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="937cb-133">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="937cb-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="937cb-134">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="937cb-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="937cb-135">Installutil.exe (инструмент для установки)</span><span class="sxs-lookup"><span data-stu-id="937cb-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
