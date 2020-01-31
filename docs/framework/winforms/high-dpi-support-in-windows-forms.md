---
title: Поддержка высокого разрешения
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741897"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="75ba6-102">Поддержка высокого DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75ba6-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="75ba6-103">Начиная с .NET Framework 4,7 Windows Forms включает улучшения для распространенных сценариев высокого и динамического DPI.</span><span class="sxs-lookup"><span data-stu-id="75ba6-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="75ba6-104">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="75ba6-104">These include:</span></span>

- <span data-ttu-id="75ba6-105">Улучшения в масштабировании и компоновке нескольких элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления и элемент управления <xref:System.Windows.Forms.CheckedListBox>.</span><span class="sxs-lookup"><span data-stu-id="75ba6-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="75ba6-106">Масштабирование с одним проходом.</span><span class="sxs-lookup"><span data-stu-id="75ba6-106">Single-pass scaling.</span></span>  <span data-ttu-id="75ba6-107">В .NET Framework 4,6 и более ранних версиях масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось.</span><span class="sxs-lookup"><span data-stu-id="75ba6-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="75ba6-108">Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.</span><span class="sxs-lookup"><span data-stu-id="75ba6-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="75ba6-109">В версиях .NET Framework, начиная с .NET Framework 4,7, расширенная поддержка высокого DPI является функцией согласия.</span><span class="sxs-lookup"><span data-stu-id="75ba6-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="75ba6-110">Необходимо настроить приложение, чтобы воспользоваться его преимуществами.</span><span class="sxs-lookup"><span data-stu-id="75ba6-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="75ba6-111">Настройка приложения Windows Forms для поддержки высокого DPI</span><span class="sxs-lookup"><span data-stu-id="75ba6-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="75ba6-112">Новые функции Windows Forms, поддерживающие распознавание высокого DPI, доступны только в приложениях, предназначенных для .NET Framework 4,7 и запущенных в операционных системах Windows, начиная с обновления Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="75ba6-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="75ba6-113">Кроме того, чтобы настроить поддержку высокого DPI в приложении Windows Forms, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75ba6-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="75ba6-114">Объявление совместимости с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="75ba6-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="75ba6-115">Для этого добавьте в файл манифеста следующее:</span><span class="sxs-lookup"><span data-stu-id="75ba6-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="75ba6-116">Включение отслеживания DPI для каждого монитора в файле *app. config* .</span><span class="sxs-lookup"><span data-stu-id="75ba6-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="75ba6-117">В Windows Forms введен новый элемент [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) для поддержки новых функций и настроек, добавленных начиная с .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="75ba6-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="75ba6-118">Чтобы воспользоваться преимуществами новых функций, поддерживающих высокое разрешение, добавьте в файл конфигурации приложения следующее:</span><span class="sxs-lookup"><span data-stu-id="75ba6-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="75ba6-119">В предыдущих версиях .NET Framework использовался манифест для добавления поддержки высокого DPI.</span><span class="sxs-lookup"><span data-stu-id="75ba6-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="75ba6-120">Этот подход больше не рекомендуется, так как он переопределяет параметры, определенные в файле App. config.</span><span class="sxs-lookup"><span data-stu-id="75ba6-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="75ba6-121">Вызовите статический метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="75ba6-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="75ba6-122">Это должен быть первый вызов метода в точке входа приложения.</span><span class="sxs-lookup"><span data-stu-id="75ba6-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="75ba6-123">Например:</span><span class="sxs-lookup"><span data-stu-id="75ba6-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="75ba6-124">Отказ от отдельных функций высокого разрешения</span><span class="sxs-lookup"><span data-stu-id="75ba6-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="75ba6-125">При установке значения `DpiAwareness` `PerMonitorV2` включаются все функции обеспечения высокого DPI, поддерживаемые версиями .NET Framework, начиная с .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="75ba6-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="75ba6-126">Как правило, это подходит для большинства Windows Forms приложений.</span><span class="sxs-lookup"><span data-stu-id="75ba6-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="75ba6-127">Однако вы можете отказаться от одной или нескольких отдельных функций.</span><span class="sxs-lookup"><span data-stu-id="75ba6-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="75ba6-128">Наиболее важной причиной этого является то, что существующий код приложения уже обрабатывает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="75ba6-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="75ba6-129">Например, если приложение обрабатывает автоматическое масштабирование, может потребоваться отключить функцию автоматического изменения размера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="75ba6-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="75ba6-130">Список отдельных ключей и их значений см. в разделе [Windows Forms Добавление элемента конфигурации](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="75ba6-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="75ba6-131">Новые события изменения DPI</span><span class="sxs-lookup"><span data-stu-id="75ba6-131">New DPI change events</span></span>

<span data-ttu-id="75ba6-132">Начиная с .NET Framework 4,7, три новых события позволяют программно управлять изменениями динамического DPI:</span><span class="sxs-lookup"><span data-stu-id="75ba6-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="75ba6-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, которая возникает, когда настройка DPI для элемента управления изменяется программным способом после события изменения DPI для родительского элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="75ba6-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="75ba6-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, которая возникает, когда значение DPI для элемента управления изменяется программным способом перед событием изменения DPI для родительского элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="75ba6-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="75ba6-135"><xref:System.Windows.Forms.Form.DpiChanged>, которая возникает при изменении параметра DPI на устройстве отображения, на котором в данный момент отображается форма.</span><span class="sxs-lookup"><span data-stu-id="75ba6-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="75ba6-136">Новые вспомогательные методы и свойства</span><span class="sxs-lookup"><span data-stu-id="75ba6-136">New helper methods and properties</span></span>

<span data-ttu-id="75ba6-137">В .NET Framework 4,7 также добавляется ряд новых вспомогательных методов и свойств, которые предоставляют сведения о масштабировании DPI и позволяют выполнять масштабирование DPI.</span><span class="sxs-lookup"><span data-stu-id="75ba6-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="75ba6-138">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="75ba6-138">These include:</span></span>

- <span data-ttu-id="75ba6-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, который преобразует значение из логического устройства в пиксел.</span><span class="sxs-lookup"><span data-stu-id="75ba6-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="75ba6-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, который масштабирует растровое изображение на логическое значение DPI для устройства.</span><span class="sxs-lookup"><span data-stu-id="75ba6-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="75ba6-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, который возвращает значение DPI для текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="75ba6-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="75ba6-142">Вопросы управления версиями</span><span class="sxs-lookup"><span data-stu-id="75ba6-142">Versioning considerations</span></span>

<span data-ttu-id="75ba6-143">В дополнение к работе на .NET Framework 4,7 и Windows 10 Creators Update, приложение также может работать в среде, в которой она несовместима с усовершенствованиями с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="75ba6-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="75ba6-144">В этом случае вам потребуется разработать резервную копию приложения.</span><span class="sxs-lookup"><span data-stu-id="75ba6-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="75ba6-145">Это можно сделать для выполнения [пользовательского рисования](./controls/user-drawn-controls.md) с целью масштабирования.</span><span class="sxs-lookup"><span data-stu-id="75ba6-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="75ba6-146">Для этого необходимо также определить операционную систему, в которой выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="75ba6-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="75ba6-147">Это можно сделать с помощью кода, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="75ba6-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="75ba6-148">Обратите внимание, что приложение не будет успешно обнаруживать Windows 10, если оно не было указано в качестве поддерживаемой операционной системы в манифесте приложения.</span><span class="sxs-lookup"><span data-stu-id="75ba6-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="75ba6-149">Также можно проверить версию .NET Framework, для которой было создано приложение.</span><span class="sxs-lookup"><span data-stu-id="75ba6-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="75ba6-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="75ba6-150">See also</span></span>

- [<span data-ttu-id="75ba6-151">Windows Forms добавить элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="75ba6-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="75ba6-152">Настройка размера и масштаба формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75ba6-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
