---
title: Устранение неполадок при получении сообщения "Не удалось запустить это приложение"
description: Сведения о том, что делать, если отображается сообщение "Не удалось запустить это приложение".
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965910"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="f11eb-103">Устранение неполадок при получении сообщения об ошибке "Не удалось запустить это приложение"</span><span class="sxs-lookup"><span data-stu-id="f11eb-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="f11eb-104">Для приложений, разработанных для .NET Framework, обычно требуется, чтобы на компьютере была установлена определенная версия .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11eb-104">Applications that are developed for the .NET Framework typically require that a specific version of the .NET Framework be installed on your system.</span></span> <span data-ttu-id="f11eb-105">В некоторых случаях вы можете попытаться запустить приложение без установленной или ожидаемой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11eb-105">In some cases, you may attempt to run an application without either an installed version or the expected version of the .NET Framework present.</span></span> <span data-ttu-id="f11eb-106">В результате этого часто выводится примерно такое диалоговое окно с сообщением об ошибке:</span><span class="sxs-lookup"><span data-stu-id="f11eb-106">This often produces an error dialog box like the following:</span></span>

![Не удалось запустить это приложение.](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="f11eb-108">Это указывает на то, что выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="f11eb-108">This typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="f11eb-109">установка .NET Framework в системе повреждена;</span><span class="sxs-lookup"><span data-stu-id="f11eb-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="f11eb-110">не удалось обнаружить версию .NET Framework, необходимую для приложения.</span><span class="sxs-lookup"><span data-stu-id="f11eb-110">The version of the .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="f11eb-111">Чтобы устранить эту проблему и запустить приложение, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f11eb-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="f11eb-112">Скачайте [средство восстановления .NET Framework (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span><span class="sxs-lookup"><span data-stu-id="f11eb-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="f11eb-113">Средство запускается автоматически после завершения скачивания.</span><span class="sxs-lookup"><span data-stu-id="f11eb-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="f11eb-114">Если средство восстановления .NET Framework рекомендует какое-либо дополнительное действие, подобное показанному на следующем рисунке, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f11eb-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![Рекомендованные изменения](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="f11eb-116">В средстве восстановления .NET Framework отображается диалоговое окно, показанное на следующем рисунке, в котором указано, что изменения внесены.</span><span class="sxs-lookup"><span data-stu-id="f11eb-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="f11eb-117">Не закрывайте диалоговое окно, пока выполняется повторная попытка запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="f11eb-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="f11eb-118">Запуск должен быть выполнен успешно, если средство восстановления .NET Framework обнаружило и устранило поврежденную установку .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f11eb-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![Рекомендованные изменения](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="f11eb-120">Если приложение успешно запускается, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f11eb-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="f11eb-121">В противном случае нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f11eb-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="f11eb-122">Если вы нажали кнопку **Далее**, в средстве восстановления .NET Framework отобразится диалоговое окно, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f11eb-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="f11eb-123">Нажмите кнопку **Готово**, чтобы отправить диагностические данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f11eb-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![Не удалось устранить проблему](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="f11eb-125">Если по-прежнему не удается запустить приложение, установите последнюю версию .NET Framework, поддерживаемую вашей версией Windows, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f11eb-125">If you still cannot run the application, install the latest version of the .NET Framework supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="f11eb-126">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="f11eb-126">Windows version</span></span>|<span data-ttu-id="f11eb-127">Установка .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f11eb-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="f11eb-128">Юбилейное обновление Windows 10 или более поздние версии</span><span class="sxs-lookup"><span data-stu-id="f11eb-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="f11eb-129">Среда выполнения .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f11eb-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f11eb-130">Windows 10, Windows 10 с обновлением за ноябрь</span><span class="sxs-lookup"><span data-stu-id="f11eb-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="f11eb-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f11eb-131">.NET Framework 4.6.2</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |<span data-ttu-id="f11eb-132">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f11eb-132">Windows 8.1</span></span>|[<span data-ttu-id="f11eb-133">Среда выполнения .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f11eb-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f11eb-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f11eb-134">Windows 8</span></span>|[<span data-ttu-id="f11eb-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f11eb-135">.NET Framework 4.6.1</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |<span data-ttu-id="f11eb-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="f11eb-136">Windows 7 SP1</span></span>|[<span data-ttu-id="f11eb-137">Среда выполнения .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f11eb-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="f11eb-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="f11eb-138">Windows Vista SP2</span></span>|[<span data-ttu-id="f11eb-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f11eb-139">.NET Framework 4.6</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > <span data-ttu-id="f11eb-140">.NET Framework 4.8, предустановленная в Windows 10 с обновлением за май 2019 г.</span><span class="sxs-lookup"><span data-stu-id="f11eb-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="f11eb-141">Попытайтесь запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="f11eb-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="f11eb-142">В некоторых случаях отображается диалоговое окно, подобное приведенному ниже, с приглашением установить платформу .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="f11eb-142">In some cases, you may see a dialog box like the following, which asks you to install the .NET Framework 3.5.</span></span> <span data-ttu-id="f11eb-143">Выберите **Скачать и установить этот компонент**, чтобы установить .NET Framework 3.5, а затем запустите приложение еще раз.</span><span class="sxs-lookup"><span data-stu-id="f11eb-143">Select **Download and install this feature** to install the .NET Framework 3.5, then launch the application again.</span></span>

   ![Не удалось устранить проблему](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="f11eb-145">См. также</span><span class="sxs-lookup"><span data-stu-id="f11eb-145">See also</span></span>

- [<span data-ttu-id="f11eb-146">Требования к системе для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f11eb-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="f11eb-147">Руководство по установке .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f11eb-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="f11eb-148">Устранение неполадок с заблокированными установками и удалениями .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f11eb-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
