---
title: Установка локализованных файлов IntelliSense
description: Узнайте, как настроить компьютер, на котором ведется разработка, для использования локализованных файлов IntelliSense в проектах .NET Core в Visual Studio.
ms.date: 01/23/2020
ms.openlocfilehash: 58b462507edf953a6c28aadbb9e3239a5cbe05b2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733650"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="518bd-103">Установка локализованных файлов IntelliSense для .NET Core</span><span class="sxs-lookup"><span data-stu-id="518bd-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="518bd-104">[IntelliSense](/visualstudio/ide/using-intellisense) — это вспомогательное средство для завершения кода, доступное в различных интегрированных средах разработки (IDE), таких как Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="518bd-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="518bd-105">По умолчанию при разработке проектов .NET Core в пакет SDK входит только английская версия файлов IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="518bd-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="518bd-106">В этой статье описано, как выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="518bd-106">This article explains:</span></span>

- <span data-ttu-id="518bd-107">Установка локализованной версии файлов.</span><span class="sxs-lookup"><span data-stu-id="518bd-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="518bd-108">Изменение установки Visual Studio для использования другого языка.</span><span class="sxs-lookup"><span data-stu-id="518bd-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="518bd-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="518bd-109">Prerequisites</span></span>

- <span data-ttu-id="518bd-110">[Пакет SDK для .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="518bd-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="518bd-111">[Visual Studio 2019 версии 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="518bd-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="518bd-112">Скачивание и установка локализованных файлов IntelliSense</span><span class="sxs-lookup"><span data-stu-id="518bd-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="518bd-113">Для выполнения этой процедуры требуются права администратора для копирования файлов IntelliSense в папку установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518bd-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="518bd-114">Перейдите на страницу [скачивания файлов IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="518bd-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="518bd-115">Скачайте файл IntelliSense для нужных языка и версии.</span><span class="sxs-lookup"><span data-stu-id="518bd-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="518bd-116">Извлеките содержимое ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="518bd-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="518bd-117">Перейдите в папку Intellisense для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518bd-117">Navigate to the .NET Core Intellisense folder.</span></span>

   1. <span data-ttu-id="518bd-118">Перейдите в папку установки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="518bd-118">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="518bd-119">Ее расположение по умолчанию: *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="518bd-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="518bd-120">Выберите пакет SDK, для которого необходимо установить IntelliSense, и перейдите по соответствующему пути.</span><span class="sxs-lookup"><span data-stu-id="518bd-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="518bd-121">Можно выбрать один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="518bd-121">You have the following options:</span></span>

      | <span data-ttu-id="518bd-122">Тип пакета SDK</span><span class="sxs-lookup"><span data-stu-id="518bd-122">SDK type</span></span>        | <span data-ttu-id="518bd-123">Path</span><span class="sxs-lookup"><span data-stu-id="518bd-123">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="518bd-124">.NET Core</span><span class="sxs-lookup"><span data-stu-id="518bd-124">.NET Core</span></span>       | <span data-ttu-id="518bd-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="518bd-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="518bd-126">Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="518bd-126">Windows Desktop</span></span> | <span data-ttu-id="518bd-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="518bd-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="518bd-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="518bd-128">.NET Standard</span></span>   | <span data-ttu-id="518bd-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="518bd-129">*NETStandard.Library.Ref*</span></span>          |
   
   1. <span data-ttu-id="518bd-130">Перейдите к версии, для которой необходимо установить локализованные файлы IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="518bd-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="518bd-131">Например, *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="518bd-131">For example, *3.1.0*.</span></span>
   1. <span data-ttu-id="518bd-132">Откройте папку *ref*.</span><span class="sxs-lookup"><span data-stu-id="518bd-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="518bd-133">Откройте папку моникера.</span><span class="sxs-lookup"><span data-stu-id="518bd-133">Open the moniker folder.</span></span> <span data-ttu-id="518bd-134">Например, *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="518bd-134">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="518bd-135">Таким образом, полный путь для перехода будет выглядеть примерно так: *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="518bd-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="518bd-136">В открытой папке моникера создайте вложенную папку.</span><span class="sxs-lookup"><span data-stu-id="518bd-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="518bd-137">Имя папки указывает, какой язык будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="518bd-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="518bd-138">В следующей таблице приводятся различные варианты.</span><span class="sxs-lookup"><span data-stu-id="518bd-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="518bd-139">Язык</span><span class="sxs-lookup"><span data-stu-id="518bd-139">Language</span></span>              | <span data-ttu-id="518bd-140">Имя папки</span><span class="sxs-lookup"><span data-stu-id="518bd-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="518bd-141">Португальский (Бразилия)</span><span class="sxs-lookup"><span data-stu-id="518bd-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="518bd-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="518bd-142">*pt-br*</span></span>     |
   | <span data-ttu-id="518bd-143">Китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="518bd-143">Chinese (simplified)</span></span>  | <span data-ttu-id="518bd-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="518bd-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="518bd-145">Китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="518bd-145">Chinese (traditional)</span></span> | <span data-ttu-id="518bd-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="518bd-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="518bd-147">Французский</span><span class="sxs-lookup"><span data-stu-id="518bd-147">French</span></span>                | <span data-ttu-id="518bd-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="518bd-148">*fr*</span></span>        |
   | <span data-ttu-id="518bd-149">Немецкий</span><span class="sxs-lookup"><span data-stu-id="518bd-149">German</span></span>                | <span data-ttu-id="518bd-150">*de*</span><span class="sxs-lookup"><span data-stu-id="518bd-150">*de*</span></span>        |
   | <span data-ttu-id="518bd-151">Итальянский</span><span class="sxs-lookup"><span data-stu-id="518bd-151">Italian</span></span>               | <span data-ttu-id="518bd-152">*it*</span><span class="sxs-lookup"><span data-stu-id="518bd-152">*it*</span></span>        |
   | <span data-ttu-id="518bd-153">Японский</span><span class="sxs-lookup"><span data-stu-id="518bd-153">Japanese</span></span>              | <span data-ttu-id="518bd-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="518bd-154">*ja*</span></span>        |
   | <span data-ttu-id="518bd-155">Корейский</span><span class="sxs-lookup"><span data-stu-id="518bd-155">Korean</span></span>                | <span data-ttu-id="518bd-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="518bd-156">*ko*</span></span>        |
   | <span data-ttu-id="518bd-157">Русский</span><span class="sxs-lookup"><span data-stu-id="518bd-157">Russian</span></span>               | <span data-ttu-id="518bd-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="518bd-158">*ru*</span></span>        |
   | <span data-ttu-id="518bd-159">Испанский</span><span class="sxs-lookup"><span data-stu-id="518bd-159">Spanish</span></span>               | <span data-ttu-id="518bd-160">*es*</span><span class="sxs-lookup"><span data-stu-id="518bd-160">*es*</span></span>        |

1. <span data-ttu-id="518bd-161">Скопируйте *XML*-файлы, извлеченные на шаге 3, в эту новую папку.</span><span class="sxs-lookup"><span data-stu-id="518bd-161">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="518bd-162">*XML*-файлы распределены по папкам пакетов SDK, поэтому их следует скопировать в соответствующий пакет SDK, выбранный на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="518bd-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="518bd-163">Изменение языка Visual Studio</span><span class="sxs-lookup"><span data-stu-id="518bd-163">Modify Visual Studio language</span></span>

<span data-ttu-id="518bd-164">Чтобы в Visual Studio использовать другой язык для IntelliSense, необходимо установить соответствующий языковой пакет.</span><span class="sxs-lookup"><span data-stu-id="518bd-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="518bd-165">Это можно сделать [во время установки](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) или позднее, изменив установку Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="518bd-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="518bd-166">Если среда Visual Studio уже настроена с нужным вам языком, установка IntelliSense также будет готова.</span><span class="sxs-lookup"><span data-stu-id="518bd-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="518bd-167">Установка языкового пакета</span><span class="sxs-lookup"><span data-stu-id="518bd-167">Install the language pack</span></span>

<span data-ttu-id="518bd-168">Если нужный языковой пакет не был установлен, обновите Visual Studio, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="518bd-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="518bd-169">Чтобы установить, обновить или изменить среду Visual Studio, необходимо войти в учетную запись с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="518bd-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="518bd-170">Дополнительные сведения см. в статье [Разрешения пользователей и Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="518bd-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="518bd-171">Найдите установщик Visual Studio на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="518bd-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="518bd-172">Например, на компьютере с Windows 10 нажмите кнопку **Пуск** и прокрутите список до буквы **V**, где расположен пункт **Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="518bd-172">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Открытие Visual Studio Installer в Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="518bd-174">Кроме того, Visual Studio Installer можно найти в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="518bd-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="518bd-175">Для продолжения работы может потребоваться обновление самого установщика.</span><span class="sxs-lookup"><span data-stu-id="518bd-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="518bd-176">Если это так, следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="518bd-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="518bd-177">В установщике найдите установленный у вас выпуск Visual Studio, для которого нужно добавить языковой пакет, и щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="518bd-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Обновление или изменение Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="518bd-179">Если кнопка **Изменить** отсутствует, но доступна кнопка **Обновить**, необходимо обновить Visual Studio и лишь затем изменить установку.</span><span class="sxs-lookup"><span data-stu-id="518bd-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="518bd-180">После завершения обновления должна появиться кнопка **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="518bd-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="518bd-181">На вкладке **Языковые пакеты** выберите языки, которые нужно установить, или отмените выбор тех, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="518bd-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Вкладка "Языковые пакеты" в Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="518bd-183">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="518bd-183">Choose **Modify**.</span></span> <span data-ttu-id="518bd-184">Начнется обновление.</span><span class="sxs-lookup"><span data-stu-id="518bd-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="518bd-185">Изменение языковых параметров в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="518bd-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="518bd-186">После установки нужных языковых пакетов измените параметры Visual Studio для использования другого языка, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="518bd-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="518bd-187">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="518bd-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="518bd-188">В начальном окне выберите **Продолжить без кода**.</span><span class="sxs-lookup"><span data-stu-id="518bd-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="518bd-189">В строке меню выберите **Сервис** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="518bd-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="518bd-190">Откроется диалоговое окно "Параметры ".</span><span class="sxs-lookup"><span data-stu-id="518bd-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="518bd-191">В узле **Среда** выберите **Выбор языка**.</span><span class="sxs-lookup"><span data-stu-id="518bd-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="518bd-192">В раскрывающемся списке **Язык** выберите язык.</span><span class="sxs-lookup"><span data-stu-id="518bd-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="518bd-193">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="518bd-193">Choose **OK**.</span></span> 

1. <span data-ttu-id="518bd-194">Появится диалоговое окно, информирующее о необходимости перезапуска Visual Studio для применения изменений.</span><span class="sxs-lookup"><span data-stu-id="518bd-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="518bd-195">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="518bd-195">Choose **OK**.</span></span>

1. <span data-ttu-id="518bd-196">Перезапустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="518bd-196">Restart Visual Studio.</span></span>

<span data-ttu-id="518bd-197">Теперь при открытии проекта .NET Core, предназначенного для версии только что установленных файлов IntelliSense, средство IntelliSense должно работать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="518bd-197">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="518bd-198">См. также</span><span class="sxs-lookup"><span data-stu-id="518bd-198">See also</span></span>

- [<span data-ttu-id="518bd-199">IntelliSense в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="518bd-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
