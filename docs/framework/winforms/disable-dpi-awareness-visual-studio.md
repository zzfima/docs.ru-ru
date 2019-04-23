---
title: Отключение поддержки определения DPI в Visual Studio
description: Описывает ограничения части конструктора Windows Forms на HDPI-мониторах и запуска Visual Studio в качестве процесса не поддерживают DPI.
ms.date: 04/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.custom: seoapril2019
ms.openlocfilehash: e52debea382033417afe0bd47f899af1666192bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181388"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a><span data-ttu-id="60f9b-103">Отключение поддержки определения DPI в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="60f9b-103">Disable DPI-awareness in Visual Studio</span></span>

<span data-ttu-id="60f9b-104">Visual Studio является точек на дюйм (DPI) приложения, что означает отображение шкалы автоматически.</span><span class="sxs-lookup"><span data-stu-id="60f9b-104">Visual Studio is a dots per inch (DPI) aware application, which means the display scales automatically.</span></span> <span data-ttu-id="60f9b-105">Если приложение указано, что он не поддерживает определение DPI, операционная система масштабируется приложение в качестве растрового изображения.</span><span class="sxs-lookup"><span data-stu-id="60f9b-105">If an application states that it's not DPI-aware, the operating system scales the application as a bitmap.</span></span> <span data-ttu-id="60f9b-106">Это поведение также называется виртуализации точек на ДЮЙМ.</span><span class="sxs-lookup"><span data-stu-id="60f9b-106">This behavior is also called DPI virtualization.</span></span> <span data-ttu-id="60f9b-107">Приложение по-прежнему считает, что он выполняется на 100% масштабирования или 96 точек на дюйм.</span><span class="sxs-lookup"><span data-stu-id="60f9b-107">The application still thinks that it's running at 100% scaling, or 96 dpi.</span></span>

<span data-ttu-id="60f9b-108">В этой статье рассматриваются ограничения части конструктора Windows Forms на HDPI-мониторах и ее запуске Visual Studio как процесс не поддерживают DPI.</span><span class="sxs-lookup"><span data-stu-id="60f9b-108">This article discusses the limitations of Windows Forms Designer on HDPI monitors and how to run Visual Studio as a DPI-unaware process.</span></span>

## <a name="windows-forms-designer-on-hdpi-monitors"></a><span data-ttu-id="60f9b-109">Конструктор Windows Forms на HDPI-мониторах</span><span class="sxs-lookup"><span data-stu-id="60f9b-109">Windows Forms Designer on HDPI monitors</span></span>

<span data-ttu-id="60f9b-110">**Конструктор Windows Forms** в Visual Studio не имеет масштабирования.</span><span class="sxs-lookup"><span data-stu-id="60f9b-110">The **Windows Forms Designer** in Visual Studio doesn't have scaling support.</span></span> <span data-ttu-id="60f9b-111">При открытии некоторых форм, в результате проблем с отображением **конструктор Windows Forms** на большое число точек на дюйм (HDPI) мониторов.</span><span class="sxs-lookup"><span data-stu-id="60f9b-111">This causes display issues when you open some forms in the **Windows Forms Designer** on high dots per inch (HDPI) monitors.</span></span> <span data-ttu-id="60f9b-112">Например элементы управления могут иметь пересекаются, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="60f9b-112">For examples, controls can appear to overlap as shown in the following image:</span></span>

![Конструктор Windows Forms на мониторе HDPI](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

<span data-ttu-id="60f9b-114">При открытии формы в **конструктор Windows Forms** в Visual Studio на мониторе HDPI Visual Studio отображает желтый, информационные панели в верхней части конструктора:</span><span class="sxs-lookup"><span data-stu-id="60f9b-114">When you open a form in the **Windows Forms Designer** in Visual Studio on an HDPI monitor, Visual Studio displays a yellow informational bar at the top of the designer:</span></span>

![Информационные панели в Visual Studio, чтобы перезагрузить компьютер в режиме не поддерживают DPI](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

<span data-ttu-id="60f9b-116">Считывает сообщение **масштабирование на главном экране равен 200% (192 dpi). Это может вызвать проблемы отрисовки в окне конструктора.**</span><span class="sxs-lookup"><span data-stu-id="60f9b-116">The message reads **Scaling on your main display is set to 200% (192 dpi). This might cause rendering problems in the designer window.**</span></span>

> [!NOTE]
> <span data-ttu-id="60f9b-117">Эта информационная панель была введена в Visual Studio 2017 версии 15.8.</span><span class="sxs-lookup"><span data-stu-id="60f9b-117">This informational bar was introduced in Visual Studio 2017 version 15.8.</span></span>

<span data-ttu-id="60f9b-118">Если вы не работают в конструкторе, не требуется для настройки макета формы можно игнорировать информационные панели и продолжить работу в редакторе кода или в других типах конструкторов.</span><span class="sxs-lookup"><span data-stu-id="60f9b-118">If you aren't working in the designer and don't need to adjust the layout of your form, you can ignore the informational bar and continue working in the code editor or in other types of designers.</span></span> <span data-ttu-id="60f9b-119">(Вы также можете [отключение уведомлений](#disable-notifications) , чтобы информационные панели не отображаются.) Только **конструктор Windows Forms** снижается.</span><span class="sxs-lookup"><span data-stu-id="60f9b-119">(You can also [disable notifications](#disable-notifications) so that the informational bar doesn't continue to appear.) Only the **Windows Forms Designer** is affected.</span></span> <span data-ttu-id="60f9b-120">Если вам нужно работать в **конструктор Windows Forms**, следующий раздел поможет вам [решить проблему](#to-resolve-the-display-problem).</span><span class="sxs-lookup"><span data-stu-id="60f9b-120">If you do need to work in the **Windows Forms Designer**, the next section helps you [resolve the problem](#to-resolve-the-display-problem).</span></span>

## <a name="to-resolve-the-display-problem"></a><span data-ttu-id="60f9b-121">Для устранения проблемы отображения</span><span class="sxs-lookup"><span data-stu-id="60f9b-121">To resolve the display problem</span></span>

<span data-ttu-id="60f9b-122">Существует три способа решения проблемы отображения:</span><span class="sxs-lookup"><span data-stu-id="60f9b-122">There are three options to resolve the display problem:</span></span>

1. [<span data-ttu-id="60f9b-123">Перезапустите Visual Studio как процесс не поддерживают DPI</span><span class="sxs-lookup"><span data-stu-id="60f9b-123">Restart Visual Studio as a DPI-unaware process</span></span>](#restart-visual-studio-as-a-dpi-unaware-process)
2. [<span data-ttu-id="60f9b-124">Добавьте параметр реестра</span><span class="sxs-lookup"><span data-stu-id="60f9b-124">Add a registry entry</span></span>](#add-a-registry-entry)
3. [<span data-ttu-id="60f9b-125">Настройте дисплей масштабирование параметр до 100%</span><span class="sxs-lookup"><span data-stu-id="60f9b-125">Set your display scaling setting to 100%</span></span>](#set-your-display-scaling-setting-to-100)

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a><span data-ttu-id="60f9b-126">Перезапустите Visual Studio как процесс не поддерживают DPI</span><span class="sxs-lookup"><span data-stu-id="60f9b-126">Restart Visual Studio as a DPI-unaware process</span></span>

<span data-ttu-id="60f9b-127">Как процесс не поддерживают DPI можно перезапустить Visual Studio, выбрав параметр на желтый информационные панели.</span><span class="sxs-lookup"><span data-stu-id="60f9b-127">You can restart Visual Studio as a DPI-unaware process by selecting the option on the yellow informational bar.</span></span> <span data-ttu-id="60f9b-128">Это предпочтительный способ устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="60f9b-128">This is the preferred way of resolving the problem.</span></span>

<span data-ttu-id="60f9b-129">При запуске Visual Studio как процесс не поддерживают DPI, устранения проблем макет конструктора, но шрифты могут быть нечеткими.</span><span class="sxs-lookup"><span data-stu-id="60f9b-129">When Visual Studio runs as a DPI-unaware process, the designer layout issues are resolved, but fonts may appear blurry.</span></span> <span data-ttu-id="60f9b-130">Visual Studio отображает различные желтый информационное сообщение, когда он выполняется как процесс не поддерживают DPI, — говорит **Visual Studio выполняется как процесс не поддерживают DPI. Конструкторы WPF и XAML могут отображаться неправильно.**</span><span class="sxs-lookup"><span data-stu-id="60f9b-130">Visual Studio displays a different yellow informational message when it runs as a DPI-unaware process that says **Visual Studio is running as a DPI-unaware process. WPF and XAML designers might not display correctly.**</span></span> <span data-ttu-id="60f9b-131">Информационные панели также предоставляет возможность **перезапустите Visual Studio, как поддерживающее DPI процесс**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-131">The informational bar also provides an option to **Restart Visual Studio as a DPI-aware process**.</span></span>

> [!NOTE]
> - <span data-ttu-id="60f9b-132">Если извлечения окна инструментов в Visual Studio при выборе перезагрузите компьютер как процесс не поддерживают DPI, может измениться положения этих окон инструментов.</span><span class="sxs-lookup"><span data-stu-id="60f9b-132">If you had undocked tool windows in Visual Studio when you selected the option to restart as a DPI-unaware process, the position of those tool windows may change.</span></span>
> - <span data-ttu-id="60f9b-133">Если вы используете профиль Visual Basic по умолчанию, или у вас есть **сохранять новые проекты при создании** параметр выбран в **средства** > **параметры**  >  **Проекты и решения**, Visual Studio не удается восстановить проект после его перезапуска, как процесс не поддерживают DPI.</span><span class="sxs-lookup"><span data-stu-id="60f9b-133">If you use the default Visual Basic profile, or if you have the **Save new projects when created** option deselected in **Tools** > **Options** > **Projects and Solutions**, Visual Studio cannot reopen your project when it restarts as a DPI-unaware process.</span></span> <span data-ttu-id="60f9b-134">Тем не менее, можно открыть проект, выбрав его в разделе **файл** > **последние проекты и решения**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-134">However, you can open the project by selecting it under **File** > **Recent Projects and Solutions**.</span></span>

<span data-ttu-id="60f9b-135">Очень важно перезапустить Visual Studio как поддерживающее DPI процесс при завершении работы **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-135">It's important to restart Visual Studio as a DPI-aware process when you're finished working in the **Windows Forms Designer**.</span></span> <span data-ttu-id="60f9b-136">Когда он выполняется как процесс не поддерживают DPI, можно, выглядели нечеткими шрифты и могут возникнуть проблемы в других конструкторах например **конструктор XAML**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-136">When it's running as a DPI-unaware process, fonts can look blurry and you may see issues in other designers such as the **XAML Designer**.</span></span> <span data-ttu-id="60f9b-137">Если вы закроете и снова откройте Visual Studio при работе в режиме не поддерживают DPI, он становится дюйм еще раз.</span><span class="sxs-lookup"><span data-stu-id="60f9b-137">If you close and reopen Visual Studio when it's running in DPI-unaware mode, it becomes DPI-aware again.</span></span> <span data-ttu-id="60f9b-138">Можно также щелкнуть **перезапустите Visual Studio, как поддерживающее DPI процесс** параметр на информационные панели.</span><span class="sxs-lookup"><span data-stu-id="60f9b-138">You can also click the **Restart Visual Studio as a DPI-aware process** option in the informational bar.</span></span>

### <a name="add-a-registry-entry"></a><span data-ttu-id="60f9b-139">Добавьте параметр реестра</span><span class="sxs-lookup"><span data-stu-id="60f9b-139">Add a registry entry</span></span>

<span data-ttu-id="60f9b-140">Visual Studio можно пометить как не поддерживающие точек на ДЮЙМ, путем изменения реестра.</span><span class="sxs-lookup"><span data-stu-id="60f9b-140">You can mark Visual Studio as DPI-unaware by modifying the registry.</span></span> <span data-ttu-id="60f9b-141">Откройте **редактора реестра** и добавить запись **NT\CurrentVersion\AppCompatFlags\Layers этот** подраздел:</span><span class="sxs-lookup"><span data-stu-id="60f9b-141">Open **Registry Editor** and add an entry to the **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** subkey:</span></span>

<span data-ttu-id="60f9b-142">**Запись**: В зависимости от того, используете ли вы Visual Studio 2017 или 2019 г. Используйте одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="60f9b-142">**Entry**: Depending on whether you're using Visual Studio 2017 or 2019, use one of these values:</span></span>

- <span data-ttu-id="60f9b-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="60f9b-143">C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span></span>
- <span data-ttu-id="60f9b-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="60f9b-144">C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe</span></span>

> [!NOTE]
> <span data-ttu-id="60f9b-145">Если вы используете выпуск Visual Studio Professional или Enterprise, замените **сообщества** с **Professional** или **Enterprise** в записи.</span><span class="sxs-lookup"><span data-stu-id="60f9b-145">If you're using the Professional or Enterprise edition of Visual Studio, replace **Community** with **Professional** or **Enterprise** in the entry.</span></span> <span data-ttu-id="60f9b-146">Кроме того, замените букву диска, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="60f9b-146">Also replace the drive letter as necessary.</span></span>

<span data-ttu-id="60f9b-147">**Тип**: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="60f9b-147">**Type**: REG_SZ</span></span>

<span data-ttu-id="60f9b-148">**Значение**. DPIUNAWARE</span><span class="sxs-lookup"><span data-stu-id="60f9b-148">**Value**: DPIUNAWARE</span></span>

> [!NOTE]
> <span data-ttu-id="60f9b-149">Visual Studio остается в режиме не поддерживают DPI, пока вы не удалите запись в реестр.</span><span class="sxs-lookup"><span data-stu-id="60f9b-149">Visual Studio remains in DPI-unaware mode until you remove the registry entry.</span></span>

### <a name="set-your-display-scaling-setting-to-100"></a><span data-ttu-id="60f9b-150">Настройте дисплей масштабирование параметр до 100%</span><span class="sxs-lookup"><span data-stu-id="60f9b-150">Set your display scaling setting to 100%</span></span>

<span data-ttu-id="60f9b-151">Для применения вашего экрана, масштабирование параметр до 100% в Windows 10 введите **параметры отображения** в панели поиска, а затем выберите задач **изменению параметров отображения**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-151">To set your display scaling setting to 100% in Windows 10, type **display settings** in the task bar search box, and then select **Change display settings**.</span></span> <span data-ttu-id="60f9b-152">В **параметры** окне **изменить размер текста, приложений и других элементов** для **100%**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-152">In the **Settings** window, set **Change the size of text, apps, and other items** to **100%**.</span></span>

<span data-ttu-id="60f9b-153">Настройка вашего экрана, масштабирование до 100% может быть нежелательно, так как он может сделать пользовательский интерфейс слишком мал, чтобы можно было использовать.</span><span class="sxs-lookup"><span data-stu-id="60f9b-153">Setting your display scaling to 100% may be undesirable, because it can make the user interface too small to be usable.</span></span>

## <a name="disable-notifications"></a><span data-ttu-id="60f9b-154">Отключение уведомлений</span><span class="sxs-lookup"><span data-stu-id="60f9b-154">Disable notifications</span></span>

<span data-ttu-id="60f9b-155">Вы можете не получать уведомления о DPI масштабирование проблемы в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="60f9b-155">You can choose not to be notified of DPI scaling issues in Visual Studio.</span></span> <span data-ttu-id="60f9b-156">Может потребоваться отключить уведомления, если вы не в конструкторе, например.</span><span class="sxs-lookup"><span data-stu-id="60f9b-156">You might want to disable notifications if you aren't working in the designer, for example.</span></span>

<span data-ttu-id="60f9b-157">Чтобы отключить уведомления, выберите **средства** > **параметры** открыть **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="60f9b-157">To disable notifications, choose **Tools** > **Options** to open the **Options** dialog.</span></span> <span data-ttu-id="60f9b-158">Выберите **конструктор Windows Forms** > **Общие**и задайте **уведомления масштабирование DPI** для **False**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-158">Then, choose **Windows Forms Designer** > **General**, and set **DPI Scaling Notifications** to **False**.</span></span>

![Разрешение DPI, параметр уведомлений в Visual Studio](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

<span data-ttu-id="60f9b-160">Если требуется, чтобы позднее снова включить функцию масштабирования уведомления, присвойте свойству **True**.</span><span class="sxs-lookup"><span data-stu-id="60f9b-160">If you want to later reenable scaling notifications, set the property to **True**.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="60f9b-161">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="60f9b-161">Troubleshoot</span></span>

<span data-ttu-id="60f9b-162">Если поддержка DPI перехода не работает должным образом в Visual Studio, проверьте наличие `dpiAwareness` значение в **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image файл выполнения Options\devenv.exe**  подразделов в редакторе реестра.</span><span class="sxs-lookup"><span data-stu-id="60f9b-162">If the DPI-awareness transition isn't working as expected in Visual Studio, check to see if you have the `dpiAwareness` value in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\devenv.exe** subkey in Registry Editor.</span></span> <span data-ttu-id="60f9b-163">Удалите значение, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="60f9b-163">Delete the value if it's present.</span></span>

## <a name="see-also"></a><span data-ttu-id="60f9b-164">См. также</span><span class="sxs-lookup"><span data-stu-id="60f9b-164">See also</span></span>

- [<span data-ttu-id="60f9b-165">Автоматическое масштабирование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60f9b-165">Automatic scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
