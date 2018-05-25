---
title: Высокий уровень поддержки DPI в Windows Forms
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbf2d7b61b34a2cd4641a77ee1f2fcdff7f3c3fe
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="16aaf-102">Высокий уровень поддержки DPI в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16aaf-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="16aaf-103">Начиная с .NET Framework 4.7, Windows Forms включает улучшения для распространенных высокое разрешение и динамических сценариев точек на ДЮЙМ.</span><span class="sxs-lookup"><span data-stu-id="16aaf-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="16aaf-104">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="16aaf-104">These include:</span></span> 

- <span data-ttu-id="16aaf-105">Усовершенствования в масштабировании и макет несколько форм Windows элементы управления, такие как <xref:System.Windows.Forms.MonthCalendar> управления и <xref:System.Windows.Forms.CheckedListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="16aaf-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

- <span data-ttu-id="16aaf-106">Один с отрицательным масштабирования.</span><span class="sxs-lookup"><span data-stu-id="16aaf-106">Single-pass scaling.</span></span>  <span data-ttu-id="16aaf-107">В .NET Framework 4.6 и более ранних версий масштабирование выполнялось через несколько проходов, которые вызвала некоторые элементы управления масштабировать больше, чем необходимо.</span><span class="sxs-lookup"><span data-stu-id="16aaf-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="16aaf-108">Поддержка динамического DPI сценариев, в которых пользователь изменяет коэффициент DPI или масштаб после запуска приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="16aaf-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="16aaf-109">В версиях платформы .NET Framework, начиная с .NET Framework 4.7 расширенную поддержку высоким DPI является дополнительной функции.</span><span class="sxs-lookup"><span data-stu-id="16aaf-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="16aaf-110">Необходимо настроить приложение, чтобы воспользоваться преимуществами его.</span><span class="sxs-lookup"><span data-stu-id="16aaf-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="16aaf-111">Настройка приложения Windows Forms с высоким DPI поддержки</span><span class="sxs-lookup"><span data-stu-id="16aaf-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="16aaf-112">Новые возможности Windows Forms, которые поддерживают высокого уровня осведомленности DPI, доступны только в приложения, предназначенные для .NET Framework 4.7, работающих под управлением операционных систем Windows, начиная с обновления создатели Windows 10.</span><span class="sxs-lookup"><span data-stu-id="16aaf-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span> 

<span data-ttu-id="16aaf-113">Кроме того для настройки высокого уровня поддержки DPI в приложении Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="16aaf-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="16aaf-114">Объявите совместимости с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="16aaf-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="16aaf-115">Для этого добавьте следующее в файл манифеста:</span><span class="sxs-lookup"><span data-stu-id="16aaf-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="16aaf-116">Включение точек на ДЮЙМ на мониторе, поддерживающие *app.config* файла.</span><span class="sxs-lookup"><span data-stu-id="16aaf-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="16aaf-117">Windows Forms появилось новое [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) для поддержки новых функций и добавлены сведения о настройках, начиная с .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="16aaf-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../docs/framework/configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="16aaf-118">Чтобы воспользоваться преимуществами новых функций, которые поддерживают высокого Разрешения, добавьте следующее в файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="16aaf-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > <span data-ttu-id="16aaf-119">В предыдущих версиях платформы .NET Framework вы использовали для добавления поддержки высоким DPI манифест.</span><span class="sxs-lookup"><span data-stu-id="16aaf-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="16aaf-120">Такой подход не рекомендуется, так как он переопределяет параметры, определенные в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="16aaf-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>
   
- <span data-ttu-id="16aaf-121">Вызовите статический <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="16aaf-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>
   
  <span data-ttu-id="16aaf-122">Это должен быть первый вызов метода в точку входа приложения.</span><span class="sxs-lookup"><span data-stu-id="16aaf-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="16aaf-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="16aaf-123">For example:</span></span>
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="16aaf-124">Отказ от отдельных функций высоким DPI</span><span class="sxs-lookup"><span data-stu-id="16aaf-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="16aaf-125">Установка `DpiAwareness` значение `PerMonitorV2` включает в себя все высокого уровня осведомленности возможности DPI, поддерживается в версиях .NET Framework, начиная с .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="16aaf-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="16aaf-126">Как правило этого достаточно для большинства приложений Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="16aaf-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="16aaf-127">Однако можно отказаться от одного или нескольких отдельных функций.</span><span class="sxs-lookup"><span data-stu-id="16aaf-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="16aaf-128">Таким образом наиболее важных причина заключается в том, что существующий код приложения уже обрабатывает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="16aaf-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="16aaf-129">Например если приложение обрабатывает автоматическим масштабированием, может потребоваться отключить функцию автоподбора размера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="16aaf-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

<span data-ttu-id="16aaf-130">Список отдельных ключей и их значений см. в разделе [добавьте элемент конфигурации Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="16aaf-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="16aaf-131">Новые события изменения точек на ДЮЙМ</span><span class="sxs-lookup"><span data-stu-id="16aaf-131">New DPI change events</span></span>

<span data-ttu-id="16aaf-132">Начиная с .NET Framework 4.7, три новые события позволяют программным образом обрабатывать динамические изменения точек на ДЮЙМ.</span><span class="sxs-lookup"><span data-stu-id="16aaf-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="16aaf-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, которая возникает, когда параметр точек на ДЮЙМ для элемента управления программным способом изменяется после событие изменения DPI для его родительского элемента управления или формы произошла.</span><span class="sxs-lookup"><span data-stu-id="16aaf-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="16aaf-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, который возникает, когда параметр DPI для элемента управления изменяется программным образом перед событие изменения DPI для родительского элемента управления или формы произошла.</span><span class="sxs-lookup"><span data-stu-id="16aaf-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="16aaf-135"><xref:System.Windows.Forms.Form.DpiChanged>, который возникает, когда параметр DPI меняется на устройстве отображения, где в настоящее время отображается форма.</span><span class="sxs-lookup"><span data-stu-id="16aaf-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="16aaf-136">Новые вспомогательные методы и свойства</span><span class="sxs-lookup"><span data-stu-id="16aaf-136">New helper methods and properties</span></span>

<span data-ttu-id="16aaf-137">4.7 .NET Framework также добавляет ряд новых вспомогательные методы и свойства, которые предоставляют сведения о масштабирование и позволяют выполнять масштабирование.</span><span class="sxs-lookup"><span data-stu-id="16aaf-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="16aaf-138">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="16aaf-138">These include:</span></span>

- <span data-ttu-id="16aaf-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, который преобразует значение из логического устройства.</span><span class="sxs-lookup"><span data-stu-id="16aaf-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="16aaf-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, который масштабирует точечный рисунок логических DPI для устройства.</span><span class="sxs-lookup"><span data-stu-id="16aaf-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="16aaf-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, который возвращает DPI для текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="16aaf-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="16aaf-142">Вопросы управления версиями</span><span class="sxs-lookup"><span data-stu-id="16aaf-142">Versioning considerations</span></span>

<span data-ttu-id="16aaf-143">Наряду с выполнением на .NET Framework 4.7 и Windows 10 создатели обновление приложения также можно запускать в среде, в которой не совместимо с высоким DPI усовершенствования.</span><span class="sxs-lookup"><span data-stu-id="16aaf-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="16aaf-144">В этом случае необходимо разработать переход на резервный ресурс для приложения.</span><span class="sxs-lookup"><span data-stu-id="16aaf-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="16aaf-145">Этого можно выполнить [нестандартных операций рисования](./controls/user-drawn-controls.md) для обработки масштабирования.</span><span class="sxs-lookup"><span data-stu-id="16aaf-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="16aaf-146">Чтобы сделать это, необходимо также определить операционную систему, на котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="16aaf-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="16aaf-147">Это можно сделать с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="16aaf-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="16aaf-148">Обратите внимание, что приложение не будет определять успешно Windows 10, если она не была указана как поддерживаемой операционной системы в манифесте приложения.</span><span class="sxs-lookup"><span data-stu-id="16aaf-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="16aaf-149">Можно также проверить версию платформы .NET Framework, в которой было создано приложение:</span><span class="sxs-lookup"><span data-stu-id="16aaf-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="16aaf-150">См. также</span><span class="sxs-lookup"><span data-stu-id="16aaf-150">See also</span></span>

[<span data-ttu-id="16aaf-151">Windows Forms добавьте элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="16aaf-151">Windows Forms Add Configuration Element</span></span>](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[<span data-ttu-id="16aaf-152">Настройка размера и масштаба формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16aaf-152">Adjusting the Size and Scale of Windows Forms</span></span>](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
