---
title: Установка построителя моделей
description: Сведения об установке построителя моделей ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b87f712ad7a8b2229c1d42db4bad1fe511475ac7
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552939"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="cf779-103">Установка построителя моделей ML.NET</span><span class="sxs-lookup"><span data-stu-id="cf779-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="cf779-104">Узнайте, как установить построитель моделей ML.NET, чтобы добавить в приложения .NET возможности машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="cf779-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="cf779-105">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="cf779-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf779-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cf779-106">Prerequisites</span></span>

- <span data-ttu-id="cf779-107">Visual Studio 2017 версии 15.9.12 или более поздней/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="cf779-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="cf779-108">Пакет SDK для .NET Core 2.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="cf779-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="cf779-109">Пакет SDK для .NET Core 3.0 сейчас не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cf779-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="cf779-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cf779-110">Limitations</span></span>

- <span data-ttu-id="cf779-111">Расширение ML.NET "Построитель моделей" в настоящее время работает только в Visual Studio для Windows.</span><span class="sxs-lookup"><span data-stu-id="cf779-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="cf779-112">Максимальный размер набора данных для обучения — 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="cf779-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="cf779-113">Максимальное количество строк для обучения в SQL Server составляет 100 тысяч.</span><span class="sxs-lookup"><span data-stu-id="cf779-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="cf779-114">Средства Microsoft SQL Server Data Tools для Visual Studio 2017 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="cf779-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="cf779-115">Установка</span><span class="sxs-lookup"><span data-stu-id="cf779-115">Install</span></span>

<span data-ttu-id="cf779-116">Построитель моделей ML.NET можно установить из Visual Studio Marketplace или из самой среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf779-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="cf779-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="cf779-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="cf779-118">Скачайте расширение из [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07).</span><span class="sxs-lookup"><span data-stu-id="cf779-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="cf779-119">Следуйте указаниям по установке в соответствующей версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf779-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="cf779-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cf779-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="cf779-121">В строке меню выберите **Сервис** > **Расширения и обновления**.</span><span class="sxs-lookup"><span data-stu-id="cf779-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017: открытие диалогового окна менеджера расширений](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="cf779-123">В окне *Расширения и обновления* выберите узел *В сети*.</span><span class="sxs-lookup"><span data-stu-id="cf779-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="cf779-124">В поле поиска выполните поиск по запросу *Построитель моделей ML.NET* и выберите в результатах пункт "Построитель моделей ML.NET (предварительная версия)".</span><span class="sxs-lookup"><span data-stu-id="cf779-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017: поиск и установка расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="cf779-126">Следуйте указаниям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="cf779-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="cf779-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="cf779-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="cf779-128">Выберите в строке меню **Расширения** > **Управление расширениями**.</span><span class="sxs-lookup"><span data-stu-id="cf779-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019: открытие диалогового окна менеджера расширений](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="cf779-130">В окне *Расширения и обновления* выберите узел *В сети*.</span><span class="sxs-lookup"><span data-stu-id="cf779-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="cf779-131">В поле поиска введите *Построитель моделей ML.NET* и выберите пункт "Построитель моделей ML.NET (предварительная версия)".</span><span class="sxs-lookup"><span data-stu-id="cf779-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019: поиск и установка расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="cf779-133">Следуйте указаниям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="cf779-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="cf779-134">Удалить</span><span class="sxs-lookup"><span data-stu-id="cf779-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="cf779-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cf779-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="cf779-136">В строке меню выберите **Сервис** > **Расширения и обновления**.</span><span class="sxs-lookup"><span data-stu-id="cf779-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017: открытие диалогового окна управления расширениями](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="cf779-138">В окне *Расширения и обновления* разверните узел *Установленные* и выберите элемент *Средства*.</span><span class="sxs-lookup"><span data-stu-id="cf779-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="cf779-139">В списке средств выберите "Построитель моделей ML.NET (предварительная версия)" и нажмите кнопку *Удалить*.</span><span class="sxs-lookup"><span data-stu-id="cf779-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017: поиск и удаление расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="cf779-141">Следуйте указаниям, чтобы завершить удаление.</span><span class="sxs-lookup"><span data-stu-id="cf779-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="cf779-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="cf779-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="cf779-143">Выберите в строке меню **Расширения** > **Управление расширениями**.</span><span class="sxs-lookup"><span data-stu-id="cf779-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019: открытие диалогового окна управления расширениями](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="cf779-145">В окне *Расширения и обновления* разверните узел *Установленные* и выберите элемент *Средства*.</span><span class="sxs-lookup"><span data-stu-id="cf779-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="cf779-146">В списке средств выберите "Построитель моделей ML.NET (предварительная версия)" и нажмите кнопку *Удалить*.</span><span class="sxs-lookup"><span data-stu-id="cf779-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019: поиск и удаление расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="cf779-148">Следуйте указаниям, чтобы завершить удаление.</span><span class="sxs-lookup"><span data-stu-id="cf779-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="cf779-149">Upgrade</span><span class="sxs-lookup"><span data-stu-id="cf779-149">Upgrade</span></span>

<span data-ttu-id="cf779-150">Процесс обновления очень похож на процесс установки.</span><span class="sxs-lookup"><span data-stu-id="cf779-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="cf779-151">Скачайте последнюю версию из Visual Studio Marketplace или используйте диспетчер расширений в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cf779-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
