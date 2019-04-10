---
title: Инструкции брандмауэра
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: f1b576b4e413fa3bae70ef1eb8f8ed768e28e309
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295163"
---
# <a name="firewall-instructions"></a><span data-ttu-id="f946f-102">Инструкции брандмауэра</span><span class="sxs-lookup"><span data-stu-id="f946f-102">Firewall Instructions</span></span>
<span data-ttu-id="f946f-103">Таким образом, чтобы примеры Windows Communication Foundation (WCF) может работать, необходимо включить несколько портов и программ в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="f946f-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="f946f-104">Многие из образцов сообщаются с использованием портов в диапазоне 8000-8003 и порта 9000.</span><span class="sxs-lookup"><span data-stu-id="f946f-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="f946f-105">По умолчанию брандмауэр включен и запрещает доступ к этим портам.</span><span class="sxs-lookup"><span data-stu-id="f946f-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="f946f-106">Чтобы включить брандмауэр для примеров, завершите одну из следующих операций, в зависимости от требований и среды безопасности.</span><span class="sxs-lookup"><span data-stu-id="f946f-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
-   <span data-ttu-id="f946f-107">Вариант 1: В интерактивном режиме включите образцы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f946f-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="f946f-108">Не вносите изменения в конфигурацию брандмауэра заранее и перейдите к построению и выполнению образцов.</span><span class="sxs-lookup"><span data-stu-id="f946f-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="f946f-109">При запуске образца **предупреждение системы безопасности Windows** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f946f-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="f946f-110">Затем программу данного образца можно добавить в интерактивном режиме в незаблокированный список.</span><span class="sxs-lookup"><span data-stu-id="f946f-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="f946f-111">После этого необходимо перезагрузить образец.</span><span class="sxs-lookup"><span data-stu-id="f946f-111">With this procedure, you may have to then restart the sample.</span></span>  
  
-   <span data-ttu-id="f946f-112">Вариант 2: Включите программы образцов заранее.</span><span class="sxs-lookup"><span data-stu-id="f946f-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="f946f-113">Запуск **панель управления брандмауэра Windows** и включите программы образцов, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="f946f-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="f946f-114">Сначала необходимо построить программы, чтобы исполняемые файлы существовали.</span><span class="sxs-lookup"><span data-stu-id="f946f-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="f946f-115">Более подробные инструкции см. в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="f946f-115">You can find more detailed instructions in the following procedure.</span></span>  
  
-   <span data-ttu-id="f946f-116">Вариант 3. Включите диапазон портов заранее.</span><span class="sxs-lookup"><span data-stu-id="f946f-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="f946f-117">Запуск **брандмауэра Windows** **панели управления** и включите порты 80, 443, 8000-8003 и 9000, используемые в образцах.</span><span class="sxs-lookup"><span data-stu-id="f946f-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="f946f-118">Более подробные инструкции см. в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="f946f-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="f946f-119">Этот вариант менее безопасен, чем другие, поскольку он позволяет использовать эти порты любой программе, а не только образцам.</span><span class="sxs-lookup"><span data-stu-id="f946f-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="f946f-120">Если есть сомнения, какой вариант выбрать, используйте первый.</span><span class="sxs-lookup"><span data-stu-id="f946f-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="f946f-121">Если брандмауэр выполняется с другого поставщика, может потребоваться внести похожие изменения.</span><span class="sxs-lookup"><span data-stu-id="f946f-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f946f-122">Изменение конфигурации брандмауэра влияет на безопасность.</span><span class="sxs-lookup"><span data-stu-id="f946f-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="f946f-123">Рекомендуется записывать вносимые изменения и удалять их по завершении работы с образцами.</span><span class="sxs-lookup"><span data-stu-id="f946f-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="f946f-124">Включение программ образцов заранее</span><span class="sxs-lookup"><span data-stu-id="f946f-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="f946f-125">Постройте образец.</span><span class="sxs-lookup"><span data-stu-id="f946f-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="f946f-126">Нажмите кнопку **запустить**, нажмите кнопку **запуска**и тип `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="f946f-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="f946f-127">Откроется **панель управления брандмауэра Windows** приложения.</span><span class="sxs-lookup"><span data-stu-id="f946f-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f946f-128">Для запуска образцов, которым необходима возможность связи через брандмауэр Windows, требуется разрешение на изменение параметров брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="f946f-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="f946f-129">Если некоторые параметры брандмауэра недоступны и компьютер подключен к домену, возможно, системный администратор управляет этими параметрами через групповую политику.</span><span class="sxs-lookup"><span data-stu-id="f946f-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="f946f-130">Выполните один из следующих специфических шагов, чтобы дать программе возможность работать через брандмауэр Windows.</span><span class="sxs-lookup"><span data-stu-id="f946f-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    -   <span data-ttu-id="f946f-131">В Windows 7 или Windows Server 2008 r2, щелкните **разрешить запуск программы или компонента через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="f946f-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="f946f-132">Нажмите кнопку **изменить параметры**, разрешить **другую программу...** .</span><span class="sxs-lookup"><span data-stu-id="f946f-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    -   <span data-ttu-id="f946f-133">На [!INCLUDE[wv](../../../../includes/wv-md.md)] или [!INCLUDE[lserver](../../../../includes/lserver-md.md)], нажмите кнопку **разрешить программы через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="f946f-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="f946f-134">На **исключения** щелкните **добавить программу**.</span><span class="sxs-lookup"><span data-stu-id="f946f-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="f946f-135">Нажмите кнопку **Обзор** кнопку и выберите исполняемый файл примера, вы планируете запускать.</span><span class="sxs-lookup"><span data-stu-id="f946f-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="f946f-136">Повторите шаги 4 и 5, пока не будут добавлены все исполняемые файлы всех примеров, которые планируется выполнять.</span><span class="sxs-lookup"><span data-stu-id="f946f-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="f946f-137">Нажмите кнопку **ОК** чтобы закрыть приложение брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="f946f-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="f946f-138">Включение диапазона портов заранее</span><span class="sxs-lookup"><span data-stu-id="f946f-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="f946f-139">Нажмите кнопку **запустить**, нажмите кнопку **запуска**и тип `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="f946f-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="f946f-140">Откроется **панель управления брандмауэра Windows** приложения.</span><span class="sxs-lookup"><span data-stu-id="f946f-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="f946f-141">В Windows 7 или Windows Server 2008 R2 выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f946f-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="f946f-142">Нажмите кнопку **Дополнительные параметры** в левом столбце окна брандмауэра Windows.</span><span class="sxs-lookup"><span data-stu-id="f946f-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2.  <span data-ttu-id="f946f-143">Нажмите кнопку **правила для входящих подключений** в левом столбце.</span><span class="sxs-lookup"><span data-stu-id="f946f-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3.  <span data-ttu-id="f946f-144">Нажмите кнопку **новые правила** в правом столбце.</span><span class="sxs-lookup"><span data-stu-id="f946f-144">Click **New Rules** in the right column.</span></span>  
  
    4.  <span data-ttu-id="f946f-145">Выберите **порт** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f946f-145">Select **Port** and click **next**.</span></span>  
  
    5.  <span data-ttu-id="f946f-146">Выберите **TCP** и введите `8000, 8001, 8002, 8003, 9000, 80, 443` в **определенные локальные порты** поля.</span><span class="sxs-lookup"><span data-stu-id="f946f-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6.  <span data-ttu-id="f946f-147">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f946f-147">Click **Next**.</span></span>  
  
    7.  <span data-ttu-id="f946f-148">Выберите **разрешить подключение**и нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="f946f-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8.  <span data-ttu-id="f946f-149">Выберите **домена** и **частного**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f946f-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="f946f-150">Назовите это правило `WCF-WF 4.0 Samples`и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f946f-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="f946f-151">Нажмите кнопку **правила для исходящих подключений** и повторите шаги от c до h.</span><span class="sxs-lookup"><span data-stu-id="f946f-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="f946f-152">В [!INCLUDE[wv](../../../../includes/wv-md.md)] или [!INCLUDE[lserver](../../../../includes/lserver-md.md)] выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f946f-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1.  <span data-ttu-id="f946f-153">Нажмите кнопку **разрешить программы через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="f946f-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2.  <span data-ttu-id="f946f-154">На **исключения** щелкните **добавить порт**.</span><span class="sxs-lookup"><span data-stu-id="f946f-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3.  <span data-ttu-id="f946f-155">Введите имя, введите номер порта 8000 и выберите **TCP** параметр.</span><span class="sxs-lookup"><span data-stu-id="f946f-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4.  <span data-ttu-id="f946f-156">Нажмите кнопку **изменить область** кнопку, выберите **сетевое окружение** единственным вариантом (подсеть) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f946f-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="f946f-157">Повторите шаги от B до D для портов 8001, 8002, 8003, 9000, 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="f946f-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="f946f-158">Нажмите кнопку **ОК** чтобы закрыть приложение брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="f946f-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f946f-159">Удалите все исключения брандмауэра по завершении работы с примерами.</span><span class="sxs-lookup"><span data-stu-id="f946f-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="f946f-160">Чтобы сделать это, откройте **панель управления брандмауэра Windows** приложения и удалите все программы или записи, которые были добавлены в предыдущих процедурах портов.</span><span class="sxs-lookup"><span data-stu-id="f946f-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
