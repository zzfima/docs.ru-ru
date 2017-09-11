---
title: "Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8"
description: "Сведения об установке платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8."
author: rlander
ms.author: mairaw
keywords: ".NET Framework, установка"
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.contentlocale: ru-ru
ms.lasthandoff: 08/05/2017

---

# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="0a7b8-104">Установка платформы .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8</span><span class="sxs-lookup"><span data-stu-id="0a7b8-104">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="0a7b8-105">Платформа .NET Framework 3.5 может потребоваться для запуска приложений в Windows 10, Windows 8.1 и Windows 8.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-105">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="0a7b8-106">Эти инструкции можно использовать и для более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-106">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="0a7b8-107">Установка платформы .NET Framework 3.5 по запросу</span><span class="sxs-lookup"><span data-stu-id="0a7b8-107">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="0a7b8-108">Если вы попробуете запустить приложение, которому требуется платформа .NET Framework 3.5, может появиться следующее окно настройки.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-108">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="0a7b8-109">Выберите вариант **Установить этот компонент**, чтобы включить .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-109">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="0a7b8-110">Для использования этого варианта требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-110">This option requires an Internet connection.</span></span>

![Диалоговое окно установки .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="0a7b8-112">Включение платформы .NET Framework 3.5 в панели управления</span><span class="sxs-lookup"><span data-stu-id="0a7b8-112">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="0a7b8-113">Вы можете самостоятельно включить .NET Framework 3.5 через панель управления Windows.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-113">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="0a7b8-114">Для использования этого варианта требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-114">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="0a7b8-115">Нажмите клавишу Windows ![с логотипом Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) на клавиатуре, введите "Компоненты Windows" и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-115">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="0a7b8-116">Откроется диалоговое окно **Включение и отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-116">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="0a7b8-117">Установите флажок **.NET Framework 3.5 (включает .NET 2.0 и 3.0)**, нажмите кнопку **OK** и перезагрузите компьютер при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-117">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Установка .NET с помощью панели управления](./media/dotnet-control-panel.png)

   <span data-ttu-id="0a7b8-119">Дочерние элементы для **активации Windows Communication Foundation (WCF) по HTTP** и **активации Windows Communication Foundation (WCF) по протоколу, отличному от HTTP**, предназначены для разработчиков и администраторов серверов, которые используют эту функцию. В других случаях их выбирать не нужно.</span><span class="sxs-lookup"><span data-stu-id="0a7b8-119">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

