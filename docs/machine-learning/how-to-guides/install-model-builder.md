---
title: Установка построителя моделей
description: Сведения об установке построителя моделей ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306328"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="2304c-103">Установка построителя моделей ML.NET</span><span class="sxs-lookup"><span data-stu-id="2304c-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="2304c-104">Узнайте, как установить построитель моделей ML.NET, чтобы добавить в приложения .NET возможности машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="2304c-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="2304c-105">Построитель моделей в настоящее время находится на этапе предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="2304c-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="2304c-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2304c-106">Pre-requisites</span></span>

- <span data-ttu-id="2304c-107">Visual Studio 2017 версии 15.9.12 или более поздней либо Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2304c-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="2304c-108">Пакет SDK для .NET Core 2.1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2304c-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="2304c-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2304c-109">Limitations</span></span>

- <span data-ttu-id="2304c-110">Расширение ML.NET "Построитель моделей" в настоящее время работает только в Visual Studio для Windows.</span><span class="sxs-lookup"><span data-stu-id="2304c-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="2304c-111">Максимальный размер набора данных для обучения — 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="2304c-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="2304c-112">Максимальное количество строк для обучения в SQL Server составляет 100 тысяч.</span><span class="sxs-lookup"><span data-stu-id="2304c-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="2304c-113">Средства Microsoft SQL Server Data Tools для Visual Studio 2017 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2304c-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="2304c-114">Установка</span><span class="sxs-lookup"><span data-stu-id="2304c-114">Install</span></span>

<span data-ttu-id="2304c-115">Построитель моделей ML.NET можно установить из Visual Studio Marketplace или из самой среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2304c-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="2304c-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="2304c-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="2304c-117">Скачайте расширение из [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07).</span><span class="sxs-lookup"><span data-stu-id="2304c-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="2304c-118">Следуйте указаниям по установке в соответствующей версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2304c-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="2304c-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="2304c-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="2304c-120">В строке меню выберите **Сервис** > **Расширения и обновления**.</span><span class="sxs-lookup"><span data-stu-id="2304c-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017: открытие диалогового окна менеджера расширений](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="2304c-122">В окне *Расширения и обновления* выберите узел *В сети*.</span><span class="sxs-lookup"><span data-stu-id="2304c-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="2304c-123">В поле поиска выполните поиск по запросу *Построитель моделей ML.NET* и выберите в результатах пункт "Построитель моделей ML.NET (предварительная версия)".</span><span class="sxs-lookup"><span data-stu-id="2304c-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017: поиск и установка расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="2304c-125">Следуйте указаниям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="2304c-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="2304c-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2304c-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="2304c-127">Выберите в строке меню **Расширения** > **Управление расширениями**.</span><span class="sxs-lookup"><span data-stu-id="2304c-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019: открытие диалогового окна менеджера расширений](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="2304c-129">В окне *Расширения и обновления* выберите узел *В сети*.</span><span class="sxs-lookup"><span data-stu-id="2304c-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="2304c-130">В поле поиска введите *Построитель моделей ML.NET* и выберите пункт "Построитель моделей ML.NET (предварительная версия)".</span><span class="sxs-lookup"><span data-stu-id="2304c-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019: поиск и установка расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="2304c-132">Следуйте указаниям, чтобы завершить установку.</span><span class="sxs-lookup"><span data-stu-id="2304c-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="2304c-133">Удалить</span><span class="sxs-lookup"><span data-stu-id="2304c-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="2304c-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="2304c-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="2304c-135">В строке меню выберите **Сервис** > **Расширения и обновления**.</span><span class="sxs-lookup"><span data-stu-id="2304c-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017: открытие диалогового окна управления расширениями](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="2304c-137">В окне *Расширения и обновления* разверните узел *Установленные* и выберите элемент *Средства*.</span><span class="sxs-lookup"><span data-stu-id="2304c-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="2304c-138">В списке средств выберите "Построитель моделей ML.NET (предварительная версия)" и нажмите кнопку *Удалить*.</span><span class="sxs-lookup"><span data-stu-id="2304c-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017: поиск и удаление расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="2304c-140">Следуйте указаниям, чтобы завершить удаление.</span><span class="sxs-lookup"><span data-stu-id="2304c-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="2304c-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2304c-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="2304c-142">Выберите в строке меню **Расширения** > **Управление расширениями**.</span><span class="sxs-lookup"><span data-stu-id="2304c-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019: открытие диалогового окна управления расширениями](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="2304c-144">В окне *Расширения и обновления* разверните узел *Установленные* и выберите элемент *Средства*.</span><span class="sxs-lookup"><span data-stu-id="2304c-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="2304c-145">В списке средств выберите "Построитель моделей ML.NET (предварительная версия)" и нажмите кнопку *Удалить*.</span><span class="sxs-lookup"><span data-stu-id="2304c-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019: поиск и удаление расширения построителя модели в диалоговом окне менеджера расширений](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="2304c-147">Следуйте указаниям, чтобы завершить удаление.</span><span class="sxs-lookup"><span data-stu-id="2304c-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="2304c-148">Upgrade</span><span class="sxs-lookup"><span data-stu-id="2304c-148">Upgrade</span></span>

<span data-ttu-id="2304c-149">Процесс обновления очень похож на процесс установки.</span><span class="sxs-lookup"><span data-stu-id="2304c-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="2304c-150">Скачайте последнюю версию из Visual Studio Marketplace или используйте диспетчер расширений в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2304c-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
