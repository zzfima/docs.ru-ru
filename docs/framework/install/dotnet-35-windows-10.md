---
title: "Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8"
description: "Сведения об установке платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8."
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.workload:
- dotnet
ms.openlocfilehash: e81008eca3019860789db548d40998a7a7565d31
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="69618-103">Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8</span><span class="sxs-lookup"><span data-stu-id="69618-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="69618-104">Платформа .NET Framework 3.5 может потребоваться для запуска приложений в Windows 10, Windows 8.1 и Windows 8.</span><span class="sxs-lookup"><span data-stu-id="69618-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="69618-105">Эти инструкции можно использовать и для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="69618-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="69618-106">Установка платформы .NET Framework 3.5 по запросу</span><span class="sxs-lookup"><span data-stu-id="69618-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="69618-107">Если вы попробуете запустить приложение, которому требуется платформа .NET Framework 3.5, может появиться следующее окно настройки.</span><span class="sxs-lookup"><span data-stu-id="69618-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="69618-108">Выберите вариант **Установить этот компонент**, чтобы включить .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="69618-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="69618-109">Для использования этого варианта требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="69618-109">This option requires an Internet connection.</span></span>

![Диалоговое окно установки .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="69618-111">Включение платформы .NET Framework 3.5 в панели управления</span><span class="sxs-lookup"><span data-stu-id="69618-111">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="69618-112">Вы можете самостоятельно включить .NET Framework 3.5 через панель управления Windows.</span><span class="sxs-lookup"><span data-stu-id="69618-112">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="69618-113">Для использования этого варианта требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="69618-113">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="69618-114">Нажмите клавишу Windows ![с логотипом Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) на клавиатуре, введите "Компоненты Windows" и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="69618-114">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="69618-115">Откроется диалоговое окно **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="69618-115">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="69618-116">Установите флажок **.NET Framework 3.5 (включает .NET 2.0 и 3.0)**, нажмите кнопку **OK** и перезагрузите компьютер при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="69618-116">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Установка .NET с помощью панели управления](./media/dotnet-control-panel.png)

   <span data-ttu-id="69618-118">Дочерние элементы для **активации Windows Communication Foundation (WCF) по HTTP** и **активации Windows Communication Foundation (WCF) по протоколу, отличному от HTTP**, предназначены для разработчиков и администраторов серверов, которые используют эту функцию. В других случаях их выбирать не нужно.</span><span class="sxs-lookup"><span data-stu-id="69618-118">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="69618-119">Устранение неполадок с установкой .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="69618-119">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="69618-120">Во время установки могут возникнуть ошибки 0x800f0906, 0x800f0907, 0x800f081f или 0x800F0922. В этом случае обратитесь к разделу [Ошибка установки .NET Framework 3.5: 0x800f0906, 0x800f0907 или 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09).</span><span class="sxs-lookup"><span data-stu-id="69618-120">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="69618-121">Если ни один из способов, приведенных в предыдущей статье, не подходит или у вас нет подключения к Интернету, необходимо использовать установочный носитель Windows.</span><span class="sxs-lookup"><span data-stu-id="69618-121">If any of the methods discussed in the previous article fail or if you don't have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="69618-122">Дополнительные сведения см. в разделе [Развертывание .NET Framework 3.5 с помощью системы обслуживания образов развертывания и управления ими (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span><span class="sxs-lookup"><span data-stu-id="69618-122">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="69618-123">Если у вас нет установочного носителя, см. сведения в разделе [Создание установочного носителя Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span><span class="sxs-lookup"><span data-stu-id="69618-123">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>
