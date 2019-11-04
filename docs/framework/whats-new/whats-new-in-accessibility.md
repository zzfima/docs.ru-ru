---
title: Улучшения специальных возможностей в .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: 22d70d0ee976d9c1a6aabd57e5d13dc70cd2d081
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454258"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="b4b32-102">Улучшения специальных возможностей в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4b32-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="b4b32-103">Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="b4b32-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="b4b32-104">Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="b4b32-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="b4b32-105">Начиная с .NET Framework 4.7.1 платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-105">Starting with .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="b4b32-106">Переключатель специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="b4b32-106">Accessibility switches</span></span>

<span data-ttu-id="b4b32-107">Вы можете включить в приложении функции специальных возможностей, если оно предназначено для .NET Framework 4.7 или более ранней версии, но выполняется на платформе .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b4b32-107">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="b4b32-108">Вы также можете настроить в приложении использование компонентов прежних версий (и не использовать преимущества функций специальных возможностей), если оно предназначено для .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b4b32-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="b4b32-109">У каждой версии платформы .NET Framework с функциями специальных возможностей есть специальный переключатель, который можно добавить в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="b4b32-110">Ниже приведены поддерживаемые переключатели:</span><span class="sxs-lookup"><span data-stu-id="b4b32-110">The following are the supported switches:</span></span>

|<span data-ttu-id="b4b32-111">Version</span><span class="sxs-lookup"><span data-stu-id="b4b32-111">Version</span></span>|<span data-ttu-id="b4b32-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="b4b32-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="b4b32-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b4b32-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="b4b32-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="b4b32-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="b4b32-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="b4b32-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="b4b32-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="b4b32-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="b4b32-117">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="b4b32-117">.NET Framework 4.8</span></span>|<span data-ttu-id="b4b32-118">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="b4b32-118">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="b4b32-119">Использование преимуществ усовершенствованных специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="b4b32-119">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="b4b32-120">Новые специальные возможности включены по умолчанию для приложений, предназначенных для .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b4b32-120">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="b4b32-121">Кроме того, приложения, которые предназначены для более ранней версии .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей). Для этого добавьте параметры в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установите для них значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-121">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="b4b32-122">В следующем примере показано, как принять усовершенствованные специальные возможности, представленные в .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="b4b32-122">The following shows how to opt in to accessibility enhancements introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="b4b32-123">Если вы решили включить функции специальных возможностей из более поздней версии .NET Framework, необходимо явным образом включить эти функции из более ранних версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b4b32-123">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="b4b32-124">Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1 и 4.7.2 требуется следующий элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="b4b32-124">Configuring your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="b4b32-125">Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1, 4.7.2 и 4.8 требуется следующий элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="b4b32-125">Configuring your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, and 4.8 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="b4b32-126">Восстановление поведения из предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="b4b32-126">Restoring legacy behavior</span></span>

<span data-ttu-id="b4b32-127">Для приложений, ориентированных на версии .NET Framework, начиная с 4.7.1, можно отключить функции специальных возможностей, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установив значение `true`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-127">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="b4b32-128">Например, следующая конфигурация задает отказ от функций специальных возможностей, представленных в .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="b4b32-128">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="b4b32-129">Улучшения специальных возможностей в .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="b4b32-129">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="b4b32-130">Платформа .NET Framework 4.8 включает новые функции специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="b4b32-130">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="b4b32-131">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-131">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="b4b32-132">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-132">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="b4b32-133">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-133">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a><span data-ttu-id="b4b32-134">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-134">Windows Forms</span></span>

<span data-ttu-id="b4b32-135">В .NET Framework 4.8 ко многим часто используемым элементам управления Windows Forms добавлена поддержка динамических областей и событий уведомлений.</span><span class="sxs-lookup"><span data-stu-id="b4b32-135">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="b4b32-136">Кроме того, добавлена поддержка подсказок при переходе к элементам управления с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-136">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="b4b32-137">**Поддержка динамических областей для элементов управления типа Label и StatusStrip в модели автоматизации пользовательского интерфейса Microsoft Windows**</span><span class="sxs-lookup"><span data-stu-id="b4b32-137">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="b4b32-138">Динамические области в модели автоматизации пользовательского интерфейса Microsoft Windows позволяют разработчикам приложений уведомлять средства чтения с экрана об изменении текста в элементах управления, который находятся не там, где пользователь работает в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="b4b32-138">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="b4b32-139">Например, это полезно в случае с элементом управления <xref:System.Windows.Forms.StatusStrip>, в котором отображается состояние подключения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-139">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="b4b32-140">Разработчику может быть необходимо уведомить средство чтения с экрана об изменении состояния, например утере подключения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-140">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="b4b32-141">Начиная с .NET Framework 4.8 динамические области в модели автоматизации пользовательского интерфейса Microsoft Windows реализованы для элементов управления Windows Forms <xref:System.Windows.Forms.Label> и <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-141">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="b4b32-142">Например, в следующем коде динамическая область используется в элементе управления <xref:System.Windows.Forms.Label> с именем `label1`:</span><span class="sxs-lookup"><span data-stu-id="b4b32-142">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="b4b32-143">Экранный диктор произносит "Готово" независимо от того, с каким элементом в приложении взаимодействует пользователь.</span><span class="sxs-lookup"><span data-stu-id="b4b32-143">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="b4b32-144">Вы также можете реализовать <xref:System.Windows.Forms.UserControl> как динамическую область:</span><span class="sxs-lookup"><span data-stu-id="b4b32-144">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

<span data-ttu-id="b4b32-145">**События уведомлений в модели автоматизации пользовательского интерфейса Microsoft Windows**</span><span class="sxs-lookup"><span data-stu-id="b4b32-145">**UIA notification events**</span></span>

<span data-ttu-id="b4b32-146">Событие уведомления модели автоматизации пользовательского интерфейса Microsoft Windows, появившееся в Windows 10 Fall Creators Update, позволяет приложению создавать событие модели автоматизации пользовательского интерфейса, вследствие которого экранный диктор произносит текст, предоставленный с событием, причем соответствующий элемент управления в пользовательском интерфейсе не требуется.</span><span class="sxs-lookup"><span data-stu-id="b4b32-146">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="b4b32-147">В некоторых случаях это очень простой способ радикально улучшить доступность приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-147">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="b4b32-148">Он также может быть полезен для уведомления о ходе выполнения длительного процесса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-148">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="b4b32-149">Дополнительные сведения о событиях уведомлений в модели автоматизации пользовательского интерфейса Microsoft Windows см. в записи блога [Can your desktop app leverage the new UI Notification event?](https://blogs.msdn.microsoft.com/winuiautomation/2017/11/08/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need/) (Может ли ваше классическое приложение использовать новое событие уведомления пользовательского интерфейса?).</span><span class="sxs-lookup"><span data-stu-id="b4b32-149">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](https://blogs.msdn.microsoft.com/winuiautomation/2017/11/08/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need/).</span></span>

<span data-ttu-id="b4b32-150">В следующем примере создается [событие уведомления](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span><span class="sxs-lookup"><span data-stu-id="b4b32-150">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="b4b32-151">**Подсказки при доступе с клавиатуры**</span><span class="sxs-lookup"><span data-stu-id="b4b32-151">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="b4b32-152">В приложениях для платформы .NET Framework 4.7.2 и более ранних версий [подсказка](xref:System.Windows.Forms.ToolTip) элемента управления всплывает только при наведении на элемент указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="b4b32-152">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="b4b32-153">Начиная с .NET Framework 4.8 подсказка также может всплывать, когда пользователь переводит фокус на элемент управления с помощью клавиши TAB или клавиш со стрелками с клавишами-модификаторами или без них.</span><span class="sxs-lookup"><span data-stu-id="b4b32-153">Starting with .NET Framework 4.8, a keyboard user can trigger a control’s tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="b4b32-154">Для данного улучшения специальных возможностей требуется дополнительный [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="b4b32-154">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="b4b32-155">На изображении ниже показана подсказка, появляющаяся, когда пользователь выбирает кнопку с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-155">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![Подсказка, появляющаяся, когда пользователь переходит к кнопке с помощью клавиатуры](./media/tooltip.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="b4b32-157">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-157">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="b4b32-158">Начиная с .NET Framework 4.8 в WPF внесен ряд улучшений специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="b4b32-158">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="b4b32-159">**Экранные дикторы больше не объявляют элементы с состоянием видимости Collapsed или Hidden**</span><span class="sxs-lookup"><span data-stu-id="b4b32-159">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="b4b32-160">Свернутые или скрытые элементы больше не объявляются средством чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="b4b32-160">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="b4b32-161">Если элементы, свойство Visibility которых имеет значение <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> или <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType>, объявляются средством чтения с экрана, пользователь может получать неправильное представление о пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-161">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="b4b32-162">Начиная с .NET Framework 4.8 в WPF свернутые или скрытые элементы больше не включаются в представление элементов управления дерева UIAutomation, поэтому средства чтения с экрана больше не могут объявлять их.</span><span class="sxs-lookup"><span data-stu-id="b4b32-162">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="b4b32-163">**Свойство SelectionTextBrush для выделения текста без использования декоративного элемента**</span><span class="sxs-lookup"><span data-stu-id="b4b32-163">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="b4b32-164">В .NET Framework 4.7.2 в WPF появилась возможность отрисовывать выделение текста в <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> без использования слоя декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="b4b32-164">In the .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="b4b32-165">В таком случае цвет переднего плана выделенного текста определялся свойством <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-165">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b4b32-166">В .NET Framework 4.8 добавлено новое свойство `SelectionTextBrush`, которое позволяет разработчикам выбирать кисть для текста, выделенного без использования декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="b4b32-166">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="b4b32-167">Это свойство работает только для элементов управления, производных от <xref:System.Windows.Controls.Primitives.TextBoxBase>, и элемента управления <xref:System.Windows.Controls.PasswordBox> в приложениях WPF с включенным выделением текста без использования декоративного элемента.</span><span class="sxs-lookup"><span data-stu-id="b4b32-167">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="b4b32-168">Оно не поддерживается элементом управления <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-168">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="b4b32-169">Если выделение текста без использования декоративного элемента не включено, это свойство игнорируется.</span><span class="sxs-lookup"><span data-stu-id="b4b32-169">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="b4b32-170">Чтобы использовать это свойство, просто добавьте его в код XAML и примените соответствующую кисть или привязку.</span><span class="sxs-lookup"><span data-stu-id="b4b32-170">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="b4b32-171">В итоге выделенный текст выглядит так:</span><span class="sxs-lookup"><span data-stu-id="b4b32-171">The resulting text selection looks like this:</span></span>

![Подсказка, появляющаяся, когда пользователь переходит к кнопке с помощью клавиатуры](./media/selectiontextbrush-property.png)

<span data-ttu-id="b4b32-173">Свойства `SelectionBrush` и `SelectionTextBrush` можно использовать вместе, чтобы получить любую требуемую комбинацию цветов фона и переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b4b32-173">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="b4b32-174">**Поддержка свойства ControllerFor в модели автоматизации пользовательского интерфейса Microsoft Windows**</span><span class="sxs-lookup"><span data-stu-id="b4b32-174">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="b4b32-175">Свойство `ControllerFor` в модели автоматизации пользовательского интерфейса Microsoft Windows возвращает массив элементов автоматизации, которые управляются элементом автоматизации, поддерживающим это свойство.</span><span class="sxs-lookup"><span data-stu-id="b4b32-175">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="b4b32-176">Это свойство обычно используется для специальной возможности автозаполнения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-176">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="b4b32-177">Свойство `ControllerFor` применяется, когда элемент автоматизации влияет на одну или несколько частей пользовательского интерфейса приложения или рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="b4b32-177">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="b4b32-178">В противном случае влияние работы элемента управления сложно связать с элементами пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-178">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="b4b32-179">Эта возможность позволяет элементам управления предоставлять значение для свойства `ControllerFor`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-179">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="b4b32-180">В .NET Framework 4.8 появился новый виртуальный метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-180">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-181">Чтобы предоставить значение для свойства `ControllerFor`, просто переопределите этот метод так, чтобы он возвращал `List<AutomationPeer>` для элементов управления, которыми управляет данный объект <xref:System.Windows.Automation.Peers.AutomationPeer>:</span><span class="sxs-lookup"><span data-stu-id="b4b32-181">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

<span data-ttu-id="b4b32-182">**Подсказки при доступе с клавиатуры**</span><span class="sxs-lookup"><span data-stu-id="b4b32-182">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="b4b32-183">В .NET Framework 4.7.2 и более ранних версиях подсказки отображались только при наведении указателя мыши на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="b4b32-183">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="b4b32-184">В .NET Framework 4.8 они также появляются при наведении фокуса с помощью клавиатуры, в том числе с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="b4b32-184">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="b4b32-185">Для использования этой возможности приложение должно быть предназначено для .NET Framework 4.8 или согласиться на ее использование с помощью параметров [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` и `Switch.UseLegacyToolTipDisplay`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-185">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="b4b32-186">Вот пример файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="b4b32-186">The following is a sample application configuration file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

<span data-ttu-id="b4b32-187">После включения этой возможности подсказки будут появляться при наведении фокуса с помощью клавиатуры для всех элементов управления, имеющих подсказки.</span><span class="sxs-lookup"><span data-stu-id="b4b32-187">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="b4b32-188">Подсказка может пропадать через некоторое время или при смене фокуса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-188">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="b4b32-189">Пользователи также могут скрывать подсказки вручную с помощью нового сочетания клавиш CTRL+SHIFT+F10.</span><span class="sxs-lookup"><span data-stu-id="b4b32-189">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="b4b32-190">После закрытия подсказки ее можно отобразить снова с помощью этого же сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="b4b32-190">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="b4b32-191">[Подсказки на ленте](xref:System.Windows.Controls.Ribbon.RibbonToolTip) для элементов управления <xref:System.Windows.Controls.Ribbon.Ribbon> не появляются при наведении фокуса с помощью клавиатуры. Они отображаются только при использовании сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="b4b32-191">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="b4b32-192">**Добавлена поддержка свойств SizeOfSet и PositionInSet в модели автоматизации пользовательского интерфейса Microsoft Windows**</span><span class="sxs-lookup"><span data-stu-id="b4b32-192">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="b4b32-193">В Windows 10 появились два новых свойства модели автоматизации пользовательского интерфейса Microsoft Windows: `SizeOfSet` и `PositionInSet`. Они используются приложениями для указания количества элементов в наборе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-193">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="b4b32-194">Клиентские приложения модели автоматизации пользовательского интерфейса Microsoft Windows, такие как средства чтения с экрана, могут запрашивать эти свойства, чтобы точно представлять пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-194">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="b4b32-195">Начиная с .NET Framework 4.8 приложения WPF предоставляют доступ к этим двум свойствам модели автоматизации пользовательского интерфейса Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b4b32-195">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="b4b32-196">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="b4b32-196">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="b4b32-197">С помощью свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b4b32-197">By using dependency properties.</span></span>

  <span data-ttu-id="b4b32-198">В WPF добавлены два новых свойства зависимостей: <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-198">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-199">Разработчик может задавать их значения с помощью XAML:</span><span class="sxs-lookup"><span data-stu-id="b4b32-199">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="b4b32-200">Путем переопределения виртуальных методов AutomationPeer.</span><span class="sxs-lookup"><span data-stu-id="b4b32-200">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="b4b32-201">В класс AutomationPeer добавлены виртуальные методы <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-201">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="b4b32-202">Разработчик может указывать значения для `SizeOfSet` и `PositionInSet`, переопределяя эти методы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b4b32-202">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

<span data-ttu-id="b4b32-203">Кроме того, элементы в экземплярах <xref:System.Windows.Controls.ItemsControl> предоставляют значения для этих свойств автоматически. Разработчику делать это не требуется.</span><span class="sxs-lookup"><span data-stu-id="b4b32-203">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="b4b32-204">Если экземпляр <xref:System.Windows.Controls.ItemsControl> сгруппирован, коллекция групп представлена как набор. Каждая группа считается отдельным набором, а каждый элемент в группе указывает свое положение в ней, а также размер группы.</span><span class="sxs-lookup"><span data-stu-id="b4b32-204">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="b4b32-205">Виртуализация не влияет на автоматически задаваемые значения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-205">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="b4b32-206">Даже если элемент не реализован, он по-прежнему учитывается при определении общего размера набора и влияет на положение других элементов в наборе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-206">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="b4b32-207">Значения предоставляются автоматически, только если приложение предназначено для .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="b4b32-207">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="b4b32-208">Если приложение предназначено для более ранних версий .NET Framework, можно задать [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3`, как показано в следующем файле App.config:</span><span class="sxs-lookup"><span data-stu-id="b4b32-208">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48" />

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="b4b32-209">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-209">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="b4b32-210">В конструктор рабочих процессов в .NET Framework 4.8 внесены указанные ниже изменения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-210">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="b4b32-211">Улучшены метки case FlowSwitch при использовании экранного диктора.</span><span class="sxs-lookup"><span data-stu-id="b4b32-211">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="b4b32-212">Улучшены описания кнопок при использовании экранного диктора.</span><span class="sxs-lookup"><span data-stu-id="b4b32-212">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="b4b32-213">Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-213">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="b4b32-214">Если приложение предназначено для .NET Framework 4.7.2 или более ранней версии, эти улучшения можно активировать отдельно, установив [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` в значение `false` в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-214">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="b4b32-215">Дополнительные сведения см. в разделе [Использование преимуществ усовершенствованных специальных возможностей](#taking-advantage-of-accessibility-enhancements) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="b4b32-215">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="b4b32-216">Улучшения специальных возможностей в .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="b4b32-216">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="b4b32-217">Платформа .NET Framework 4.7.2 включает новые функции специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="b4b32-217">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="b4b32-218">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-218">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="b4b32-219">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-219">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="b4b32-220">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-220">Windows Forms</span></span>

<span data-ttu-id="b4b32-221">**Определенные в ОС цвета в темах высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="b4b32-221">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="b4b32-222">Начиная с .NET Framework 4.7.2 Windows Forms использует цвета, определенные в операционной системе, в темах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="b4b32-222">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="b4b32-223">Это влияет на следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="b4b32-223">This affects the following controls:</span></span>

- <span data-ttu-id="b4b32-224">Стрелка раскрывающегося списка элемента управления <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-224">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="b4b32-225">Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox>, у которых для параметра <xref:System.Windows.Forms.ButtonBase.FlatStyle> установлено значение <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> или <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-225">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-226">Ранее выбранные цвета текста и фона не были контрастными и текст было сложно читать.</span><span class="sxs-lookup"><span data-stu-id="b4b32-226">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="b4b32-227">Элементы управления, содержащиеся в <xref:System.Windows.Forms.GroupBox>, у которого для свойства <xref:System.Windows.Forms.Control.Enabled> установлено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-227">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="b4b32-228">Элементы управления <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> и <xref:System.Windows.Forms.ToolStripDropDownButton>, которые имеют повышенное значение контрастности яркости в режиме высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="b4b32-228">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="b4b32-229">Свойство <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> класса <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-229">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="b4b32-230">**Усовершенствования экранного диктора**</span><span class="sxs-lookup"><span data-stu-id="b4b32-230">**Narrator improvements**</span></span>

<span data-ttu-id="b4b32-231">Начиная с .NET Framework 4.7.2 усовершенствована поддержка экранного диктора:</span><span class="sxs-lookup"><span data-stu-id="b4b32-231">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="b4b32-232">Он сообщает значение свойства <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> при объявлении текста <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-232">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="b4b32-233">Он указывает, когда для свойства <xref:System.Windows.Forms.Control.Enabled> элемента <xref:System.Windows.Forms.ToolStripMenuItem> задано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-233">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="b4b32-234">Он предоставляет отзыв о состоянии флажка, если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="b4b32-234">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="b4b32-235">Порядок фокуса экранного диктора в режиме сканирования согласуется с визуальным порядком элементов управления в диалоговом окне загрузки ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="b4b32-235">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="b4b32-236">**Усовершенствования DataGridView**</span><span class="sxs-lookup"><span data-stu-id="b4b32-236">**DataGridView improvements**</span></span>

<span data-ttu-id="b4b32-237">Начиная с .NET Framework 4.7.2 элемент управления <xref:System.Windows.Forms.DataGridView> вносит следующие улучшения специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="b4b32-237">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="b4b32-238">Строки можно сортировать с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-238">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="b4b32-239">Пользователь может нажать клавишу F3, чтобы выполнить сортировку по текущему столбцу.</span><span class="sxs-lookup"><span data-stu-id="b4b32-239">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="b4b32-240">Когда <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, заголовок столбца меняет цвет для указания на текущий столбец, когда пользователь переходит по ячейкам в текущей строке.</span><span class="sxs-lookup"><span data-stu-id="b4b32-240">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="b4b32-241">Свойство <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> возвращает правильный родительский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="b4b32-241">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="b4b32-242">**Улучшенные визуальные подсказки**</span><span class="sxs-lookup"><span data-stu-id="b4b32-242">**Improved visual cues**</span></span>

- <span data-ttu-id="b4b32-243">Элементы управления <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox> с пустым свойством <xref:System.Windows.Forms.ButtonBase.Text> отображают индикатор фокуса при получении фокуса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-243">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="b4b32-244">**Улучшенная поддержка сетки свойств**</span><span class="sxs-lookup"><span data-stu-id="b4b32-244">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="b4b32-245">Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> теперь возвращают `true` для <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> свойства только в том случае, если включен элемент PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="b4b32-245">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="b4b32-246">Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> возвращают `false` для свойства <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> только в том случае, если элемент PropertyGrid может быть изменен пользователем.</span><span class="sxs-lookup"><span data-stu-id="b4b32-246">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="b4b32-247">**Улучшение навигации с помощью клавиатуры**</span><span class="sxs-lookup"><span data-stu-id="b4b32-247">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="b4b32-248">Элемент управления <xref:System.Windows.Forms.ToolStripButton> позволяет отображать фокус, если он содержится в <xref:System.Windows.Forms.ToolStripPanel>, для свойства <xref:System.Windows.Forms.ToolStripPanel.TabStop> которого задано значение `true`</span><span class="sxs-lookup"><span data-stu-id="b4b32-248">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="b4b32-249">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-249">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="b4b32-250">**Изменения элементов управления CheckBox и RadioButton**</span><span class="sxs-lookup"><span data-stu-id="b4b32-250">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="b4b32-251">В .NET Framework 4.7.1 и более ранних версий элементы управления <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> и <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> WPF имеют несогласованные и (в классической теме и теме высокой контрастности) неправильные визуальные элементы фокуса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-251">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="b4b32-252">Это происходит в случаях, когда для элементов управления не задано какое-либо содержимое.</span><span class="sxs-lookup"><span data-stu-id="b4b32-252">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="b4b32-253">Это может затруднять переход между темами и отображение визуального элемента фокуса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-253">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="b4b32-254">В .NET Framework 4.7.2 эти визуальные элементы стали более согласованными в разных темах и более видимыми в классической и контрастной темах.</span><span class="sxs-lookup"><span data-stu-id="b4b32-254">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="b4b32-255">**Элементы управления WinForms, размещенные в приложении WPF**</span><span class="sxs-lookup"><span data-stu-id="b4b32-255">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="b4b32-256">При использовании элемента управления WinForms, размещенного в приложении WPF в .NET Framework 4.7.1 и более ранних версий, пользователи не могли выйти из слоя WinForms с помощью клавиши табуляции, если первый или последний элемент управления в слое был элементом управления <xref:System.Windows.Forms.Integration.ElementHost> WPF.</span><span class="sxs-lookup"><span data-stu-id="b4b32-256">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="b4b32-257">В .NET Framework 4.7.2 пользователи теперь могут выйти из слоя WinForms с помощью клавиши табуляции.</span><span class="sxs-lookup"><span data-stu-id="b4b32-257">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="b4b32-258">Однако автоматизированные приложения, которые зависят от постоянного нахождения фокуса в слое WinForms, могут работать некорректно.</span><span class="sxs-lookup"><span data-stu-id="b4b32-258">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="b4b32-259">Улучшения специальных возможностей в .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="b4b32-259">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="b4b32-260">Платформа .NET Framework 4.7.1 включает новые функции специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="b4b32-260">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="b4b32-261">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-261">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="b4b32-262">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-262">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="b4b32-263">Веб-элементы управления ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4b32-263">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="b4b32-264">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="b4b32-264">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="b4b32-265">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-265">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="b4b32-266">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-266">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="b4b32-267">**Улучшения средств чтения с экрана**</span><span class="sxs-lookup"><span data-stu-id="b4b32-267">**Screen reader improvements**</span></span>

<span data-ttu-id="b4b32-268">Если включены улучшения специальных возможностей, .NET Framework 4.7.1 содержит следующие усовершенствования, касающиеся средств чтения с экрана:</span><span class="sxs-lookup"><span data-stu-id="b4b32-268">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="b4b32-269">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.Expander> объявлялись средствами чтения с экрана как кнопки.</span><span class="sxs-lookup"><span data-stu-id="b4b32-269">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="b4b32-270">Начиная с .NET Framework 4.7.1 они правильно объявляются как развертываемые и свертываемые группы.</span><span class="sxs-lookup"><span data-stu-id="b4b32-270">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="b4b32-271">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.DataGridCell> объявлялись средствами чтения с экрана как пользовательские.</span><span class="sxs-lookup"><span data-stu-id="b4b32-271">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="b4b32-272">Начиная с .NET Framework 4.7.1 они правильно объявляются как ячейка сетки данных (локализованная).</span><span class="sxs-lookup"><span data-stu-id="b4b32-272">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="b4b32-273">Начиная с .NET Framework 4.7.1 средства чтения с экрана объявляют имя изменяемого <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-273">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="b4b32-274">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.PasswordBox> объявлялись как "в представлении нет элементов" или имели иное неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="b4b32-274">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="b4b32-275">Начиная с .NET Framework 4.7.1 эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="b4b32-275">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="b4b32-276">**Поддержка динамических областей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="b4b32-276">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="b4b32-277">Средства чтения с экрана, такие как экранный диктор, помогают людям читать содержимое пользовательского интерфейса приложения. Обычно для этого используется преобразование текста в речь для содержимого, находящегося в фокусе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-277">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="b4b32-278">Однако если элемент пользовательского интерфейса изменяется и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения.</span><span class="sxs-lookup"><span data-stu-id="b4b32-278">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="b4b32-279">Динамические области призваны решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="b4b32-279">Live regions aim at solving this problem.</span></span> <span data-ttu-id="b4b32-280">Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента автоматизации пользовательского интерфейса о важных изменениях элемента пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-280">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="b4b32-281">После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="b4b32-281">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="b4b32-282">Для поддержки динамических областей в WPF добавлены следующие API:</span><span class="sxs-lookup"><span data-stu-id="b4b32-282">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="b4b32-283">Поля <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, которые идентифицируют свойство **LiveSetting** и событие **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-283">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="b4b32-284">Их можно задать с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="b4b32-284">They can be set by using XAML.</span></span>

- <span data-ttu-id="b4b32-285">Присоединенное свойство **AutomationProperties.LiveSetting**, уведомляющее средство чтения с экрана о том, насколько важно изменение пользовательского интерфейса для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4b32-285">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="b4b32-286">Свойство<xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, которое идентифицирует присоединенное свойство **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-286">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="b4b32-287">Метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, который можно переопределить для предоставления значения **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-287">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="b4b32-288">Методы <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, которые возвращают и задают значение **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-288">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="b4b32-289">Перечисление <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, которое определяет следующие возможные значения **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="b4b32-289">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="b4b32-290"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-290"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-291">Элемент не отправляет уведомления при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="b4b32-291">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="b4b32-292"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-292"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-293">Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="b4b32-293">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="b4b32-294"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-294"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4b32-295">Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="b4b32-295">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="b4b32-296">Вы можете создать динамическую область, задав свойство **AutomationProperties.LiveSetting** для нужного элемента, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b4b32-296">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="b4b32-297">Когда данные в динамической области изменяются и вам нужно проинформировать средство чтения с экрана, можно явно вызвать событие, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b4b32-297">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="b4b32-298">**Высокая контрастность**</span><span class="sxs-lookup"><span data-stu-id="b4b32-298">**High contrast**</span></span>

<span data-ttu-id="b4b32-299">Начиная с .NET Framework 4.7.1 внесены улучшения в функции высокой контрастности для различных элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="b4b32-299">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="b4b32-300">Теперь они видны, когда задана тема <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-300">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="b4b32-301">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="b4b32-301">These include:</span></span>

- <span data-ttu-id="b4b32-302">Элемент управления <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="b4b32-302"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="b4b32-303">Визуальный элемент фокуса для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается.</span><span class="sxs-lookup"><span data-stu-id="b4b32-303">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="b4b32-304">Визуальные элементы клавиатуры для элементов управления <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.RadioButton> также видимы.</span><span class="sxs-lookup"><span data-stu-id="b4b32-304">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="b4b32-305">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-305">For example:</span></span>

  <span data-ttu-id="b4b32-306">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-306">Before:</span></span> 

  ![Элемент управления Expander с фокусом до внесения улучшений](./media/expander-before.png)

  <span data-ttu-id="b4b32-308">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-308">After:</span></span> 

  ![Элемент управления Expander с фокусом после внесения улучшений](./media/expander-after.png)

- <span data-ttu-id="b4b32-310">Элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="b4b32-310"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="b4b32-311">Текст в элементах управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> теперь стало проще читать, когда он выбран при использовании тем с высокой контрастностью.</span><span class="sxs-lookup"><span data-stu-id="b4b32-311">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="b4b32-312">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-312">For example:</span></span>

  <span data-ttu-id="b4b32-313">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-313">Before:</span></span> 

  ![Переключатель высокой контрастности до внесения улучшений](./media/radio-button-before.png)

  <span data-ttu-id="b4b32-315">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-315">After:</span></span> 

  ![Переключатель высокой контрастности после внесения улучшений](./media/radio-button-after.png)

- <span data-ttu-id="b4b32-317">Элемент управления <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="b4b32-317"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="b4b32-318">Начиная с .NET Framework 4.7.1 граница отключенного элемента управления <xref:System.Windows.Controls.ComboBox> имеет цвет отключенного текста.</span><span class="sxs-lookup"><span data-stu-id="b4b32-318">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="b4b32-319">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-319">For example:</span></span>

  <span data-ttu-id="b4b32-320">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-320">Before:</span></span> 

  ![Отключенная граница и текст поля со списком до внесения улучшений](./media/combo-disabled-before.png)

  <span data-ttu-id="b4b32-322">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-322">After:</span></span>   

  ![Отключенная граница и текст поля со списком после внесения улучшений](./media/combo-disabled-after.png)

  <span data-ttu-id="b4b32-324">Кроме того, отключенные и находящиеся в фокусе кнопки используют правильный цвет темы.</span><span class="sxs-lookup"><span data-stu-id="b4b32-324">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="b4b32-325">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-325">Before:</span></span>

  ![Цвета темы для кнопок до внесения улучшений](./media/button-themes-before.png) 

  <span data-ttu-id="b4b32-327">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-327">After:</span></span> 

  ![Цвета темы для кнопок после внесения улучшений](./media/button-themes-after.png) 

  <span data-ttu-id="b4b32-329">Наконец, в .NET Framework 4.7 и более ранних версий установка стиля элемента управления <xref:System.Windows.Controls.ComboBox> в значение `Toolbar.ComboBoxStyleKey` приводила к тому, что стрелка раскрывающегося списка была невидимой.</span><span class="sxs-lookup"><span data-stu-id="b4b32-329">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="b4b32-330">Начиная с .NET Framework 4.7.1 эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="b4b32-330">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="b4b32-331">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-331">For example:</span></span>

  <span data-ttu-id="b4b32-332">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-332">Before:</span></span> 

  ![Toolbar.ComboBoxStyleKey до внесения улучшений](./media/comboboxstylekey-before.png) 

  <span data-ttu-id="b4b32-334">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-334">After:</span></span> 

  ![Toolbar.ComboBoxStyleKey после внесения улучшений](./media/comboboxstylekey-after.png) 

- <span data-ttu-id="b4b32-336">Элемент управления <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="b4b32-336"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="b4b32-337">Начиная с .NET Framework 4.7.1 стрелка индикатора сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> имеет правильные цвета темы.</span><span class="sxs-lookup"><span data-stu-id="b4b32-337">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="b4b32-338">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-338">For example:</span></span>

  <span data-ttu-id="b4b32-339">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-339">Before:</span></span> 

  ![Стрелка индикатора сортировки до внесения улучшений](./media/sort-indicator-before.png) 

  <span data-ttu-id="b4b32-341">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-341">After:</span></span>   

  ![Стрелка индикатора сортировки после внесения улучшений](./media/sort-indicator-after.png) 

  <span data-ttu-id="b4b32-343">Кроме того, в .NET Framework 4.7 и более ранних версий стиль ссылки по умолчанию изменялся на неправильный цвет при наведении указателя мыши в режимах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="b4b32-343">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="b4b32-344">Начиная с .NET Framework 4.7.1 эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="b4b32-344">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="b4b32-345">Аналогичным образом, столбец флажка <xref:System.Windows.Controls.DataGrid> использует ожидаемые цвета для отзывов на фокус клавиатуры начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="b4b32-345">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="b4b32-346">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-346">Before:</span></span> 

  ![Стиль ссылки по умолчанию DataGrid до внесения улучшений](./media/default-link-style-before.png) 

  <span data-ttu-id="b4b32-348">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-348">After:</span></span>    

  ![Стиль ссылки по умолчанию DataGrid после внесения улучшений](./media/default-link-style-after.png) 

<span data-ttu-id="b4b32-350">Дополнительные сведения об улучшениях специальных возможностей WPF в .NET Framework 4.7.1 см. в разделе [Улучшения специальных возможностей в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="b4b32-350">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="b4b32-351">Улучшения специальных возможностей в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b4b32-351">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="b4b32-352">В модель Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="b4b32-352">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="b4b32-353">**Улучшенное отображение в режиме высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="b4b32-353">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="b4b32-354">Начиная с .NET Framework 4.7.1 различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-354">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="b4b32-355">В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b4b32-355">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="b4b32-356">Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4b32-356">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

<span data-ttu-id="b4b32-357">Некоторые примеры изменения режима высокой контрастности:</span><span class="sxs-lookup"><span data-stu-id="b4b32-357">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="b4b32-358">Лучше читаются флажки в элементах <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-358">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="b4b32-359">Лучше читаются выбранные отключенные элементы <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-359">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="b4b32-360">Текст в выбранном <xref:System.Windows.Forms.Button> элементе управления отличается от цвета выбора.</span><span class="sxs-lookup"><span data-stu-id="b4b32-360">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="b4b32-361">Отключенный текст проще читать.</span><span class="sxs-lookup"><span data-stu-id="b4b32-361">Disabled text is easier to read.</span></span> <span data-ttu-id="b4b32-362">Например:</span><span class="sxs-lookup"><span data-stu-id="b4b32-362">For example:</span></span>

  <span data-ttu-id="b4b32-363">До:</span><span class="sxs-lookup"><span data-stu-id="b4b32-363">Before:</span></span>

  ![Отключенный текст до внесения улучшений](./media/wf-disabled-before.png) 

  <span data-ttu-id="b4b32-365">После:</span><span class="sxs-lookup"><span data-stu-id="b4b32-365">After:</span></span>

  ![Отключенный текст после внесения улучшений](./media/wf-disabled-after.png) 

- <span data-ttu-id="b4b32-367">Усовершенствования режима высокой контрастности в диалоговом окне исключения потока.</span><span class="sxs-lookup"><span data-stu-id="b4b32-367">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="b4b32-368">**Улучшенная поддержка экранного диктора**</span><span class="sxs-lookup"><span data-stu-id="b4b32-368">**Improved Narrator support**</span></span>

<span data-ttu-id="b4b32-369">Модель Windows Forms в .NET Framework 4.7.1 содержит следующие улучшения специальных возможностей для экранного диктора:</span><span class="sxs-lookup"><span data-stu-id="b4b32-369">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="b4b32-370">К элементу управления <xref:System.Windows.Forms.MonthCalendar> может обратиться как экранный диктор, так и любое другое средство автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-370">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="b4b32-371">Элемент управления <xref:System.Windows.Forms.CheckedListBox> оповещает экранный диктор об изменении состояния флажка элемента, чтобы пользователь узнал, что значение элемента списка изменилось.</span><span class="sxs-lookup"><span data-stu-id="b4b32-371">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="b4b32-372">Элемент управления <xref:System.Windows.Forms.DataGridViewCell> сообщает правильное состояние доступа только для чтения экранному диктору.</span><span class="sxs-lookup"><span data-stu-id="b4b32-372">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="b4b32-373">Теперь экранный диктор может прочитать отключенный текст <xref:System.Windows.Forms.ToolStripMenuItem>, хотя раньше он пропускал отключенные пункты меню.</span><span class="sxs-lookup"><span data-stu-id="b4b32-373">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="b4b32-374">**Улучшенная поддержка шаблонов специальных возможностей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="b4b32-374">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="b4b32-375">Начиная с .NET Framework 4.7.1 разработчики средств специальных возможностей могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms.</span><span class="sxs-lookup"><span data-stu-id="b4b32-375">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="b4b32-376">Некоторые из этих улучшений специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="b4b32-376">These accessibility improvements include:</span></span>

- <span data-ttu-id="b4b32-377"><xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="b4b32-377">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="b4b32-378"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> теперь поддерживает [шаблон переключения](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="b4b32-378">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="b4b32-379">Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="b4b32-379">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="b4b32-380">Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-380">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="b4b32-381">**Улучшенное взаимодействие с обозревателем свойств**</span><span class="sxs-lookup"><span data-stu-id="b4b32-381">**Improved property browser experience**</span></span>

<span data-ttu-id="b4b32-382">Начиная с .NET Framework 4.7.1 модель Windows Forms включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="b4b32-382">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="b4b32-383">Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.</span><span class="sxs-lookup"><span data-stu-id="b4b32-383">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="b4b32-384">Сокращение ненужных позиций табуляции.</span><span class="sxs-lookup"><span data-stu-id="b4b32-384">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="b4b32-385">Улучшенные отчеты о типах элементов управления.</span><span class="sxs-lookup"><span data-stu-id="b4b32-385">Better reporting of control types.</span></span>
- <span data-ttu-id="b4b32-386">Улучшенная работа экранного диктора.</span><span class="sxs-lookup"><span data-stu-id="b4b32-386">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="b4b32-387">Веб-элементы управления ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4b32-387">ASP.NET web controls</span></span>

<span data-ttu-id="b4b32-388">Начиная с .NET Framework 4.7.1 и Visual Studio 2017 версии 15.3 в ASP.NET улучшена работа веб-элементов управления ASP.NET с технологией специальных возможностей в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4b32-388">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="b4b32-389">Внесены следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="b4b32-389">Changes include the following:</span></span>

- <span data-ttu-id="b4b32-390">Изменения для реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления, например в диалоговом окне **Добавить поле** в мастере **представления сведений** или в диалоговом окне **Настройка ListView** в мастере **ListView**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-390">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="b4b32-391">Изменения для улучшенного отображения в режиме высокой контрастности, например в **редакторе полей страничного навигатора данных**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-391">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="b4b32-392">Изменения для улучшения навигации с помощью клавиатуры для таких элементов, как диалоговое окно **Поля** в мастере **полей страничного навигатора**, диалоговое окно **Настроить ObjectContext** или **Настроить выбор данных** в мастере **настройки источника данных**.</span><span class="sxs-lookup"><span data-stu-id="b4b32-392">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="b4b32-393">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="b4b32-393">.NET SDK Tools</span></span>

<span data-ttu-id="b4b32-394">В [редакторе конфигурации (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) и [средстве Service Trace Viewer (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) были устранены различные ошибки специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="b4b32-394">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="b4b32-395">В основном это были незначительные проблемы, например не определялось имя или некорректно реализовывались шаблоны автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4b32-395">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="b4b32-396">Многие пользователи могли не замечать неверные значения, но пользователям, использующим вспомогательные технологии, такие как средства чтения с экрана, будет проще использовать эти средства пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="b4b32-396">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="b4b32-397">Эти усовершенствования меняют предыдущее поведение, например порядок фокуса клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-397">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="b4b32-398">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="b4b32-398">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="b4b32-399">Ниже перечислены изменения специальных возможностей в конструкторе рабочих процессов:</span><span class="sxs-lookup"><span data-stu-id="b4b32-399">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="b4b32-400">Для некоторых элементов управления изменена последовательность табуляции при переходе слева направо и сверху вниз:</span><span class="sxs-lookup"><span data-stu-id="b4b32-400">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="b4b32-401">Окно инициализации корреляции для установки данных корреляции для действия <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-401">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="b4b32-402">Окно определения содержания для действий <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-402">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="b4b32-403">Большее число функций доступно с клавиатуры:</span><span class="sxs-lookup"><span data-stu-id="b4b32-403">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="b4b32-404">При редактировании свойств действия группы свойств можно сворачивать с помощью клавиатуры в том случае, если они впервые получают фокус.</span><span class="sxs-lookup"><span data-stu-id="b4b32-404">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="b4b32-405">Значки предупреждений теперь доступны с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-405">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="b4b32-406">Кнопка **Дополнительные свойства** в окне **Свойства** теперь доступна с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="b4b32-406">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="b4b32-407">Пользователи могут с помощью клавиатуры получать доступ к элементам заголовка в областях **Аргументы** и **Переменные** в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b4b32-407">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="b4b32-408">Улучшена видимость находящихся в фокусе элементов, например в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="b4b32-408">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="b4b32-409">Добавление строк в сетки данных, используемые конструктором рабочих процессов и конструкторами действий.</span><span class="sxs-lookup"><span data-stu-id="b4b32-409">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="b4b32-410">Переход по клавише TAB между полями в действиях <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-410">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="b4b32-411">Установка значений по умолчанию для переменных или аргументов</span><span class="sxs-lookup"><span data-stu-id="b4b32-411">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="b4b32-412">Средства чтения с экрана теперь правильно распознают следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="b4b32-412">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="b4b32-413">Точки останова, установленные в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b4b32-413">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="b4b32-414">Действия <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> и <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-414">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="b4b32-415">Содержимое действия <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-415">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="b4b32-416">Целевой тип действия <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-416">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="b4b32-417">Поле со списком "Исключение" и раздел Finally действия <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-417">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="b4b32-418">Поле со списком "Тип сообщений", разделитель в окне "Добавить инициализаторы корреляции", окно "Определение содержимого", а также окно "Определение корреляции" в действиях сообщений (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="b4b32-418">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="b4b32-419">Переходы и назначения переходов конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="b4b32-419">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="b4b32-420">Заметки и соединители для действий <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-420">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="b4b32-421">Контекстные меню действий, вызываемые при щелчке правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="b4b32-421">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="b4b32-422">Редакторы значений свойств, кнопка "Очистить условия поиска", кнопки сортировки "По категории" и "По алфавиту", а также диалоговое окно "Редактор выражений" в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="b4b32-422">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="b4b32-423">Величина масштаба в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b4b32-423">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="b4b32-424">Разделитель в действиях <xref:System.Activities.Statements.Parallel> и <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-424">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="b4b32-425">Действие <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="b4b32-425">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="b4b32-426">Окно "Выбор типов" для действий словаря (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="b4b32-426">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="b4b32-427">Окно поиска и выбора типа .NET.</span><span class="sxs-lookup"><span data-stu-id="b4b32-427">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="b4b32-428">Элемент иерархической навигации в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="b4b32-428">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="b4b32-429">Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости многих частей конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.</span><span class="sxs-lookup"><span data-stu-id="b4b32-429">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4b32-430">См. также</span><span class="sxs-lookup"><span data-stu-id="b4b32-430">See also</span></span>

- [<span data-ttu-id="b4b32-431">Новые возможности .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4b32-431">What's new in the .NET Framework</span></span>](index.md)
