---
title: "Новые возможности специальных возможностей в .NET Framework"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="9cbb1-102">Новые возможности специальных возможностей в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9cbb1-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="9cbb1-103">Платформа .NET Framework намеревается делать приложения более доступность для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="9cbb1-104">Специальные возможности позволяют приложению обеспечить соответствующие возможности при работе с поддержкой специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="9cbb1-105">Начиная с платформы .NET Framework 4.7.1, платформа .NET Framework включает большое количество более удобным, позволяющие разработчикам создавать приложения со специальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="9cbb1-106">Новые функции специальных возможностей будут включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="9cbb1-107">Кроме того, приложения, которые более раннюю версию платформы .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии можно выбрать поведений устаревших специальных возможностей (и тем самым согласие на использование более удобным в платформе .NET Framework 4.7.1), добавив следующий параметр для [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="9cbb1-108">Аналогичным образом, приложения, предназначенные для версий платформы .NET Framework, начиная с 4.7.1 можно отключить, добавив следующий параметр, чтобы специальные возможности [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="9cbb1-109">Новые возможности специальных возможностей в .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="9cbb1-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="9cbb1-110">Платформа .NET Framework 4.7.1 включает новые функции специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="9cbb1-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="9cbb1-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="9cbb1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cbb1-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="9cbb1-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="9cbb1-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="9cbb1-114">**Усовершенствования чтения экрана**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-114">**Screen reader improvements**</span></span>

<span data-ttu-id="9cbb1-115">Если включены более удобным, платформа .NET Framework 4.7.1 включает следующие улучшения, которые влияют на средства чтения с экрана:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="9cbb1-116">В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.Expander> элементы управления были объявлены с экрана, как кнопки.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="9cbb1-117">Начиная с платформы .NET Framework 4.7.1, они правильно воспринимаются как расширяемые и свертываемые группы.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="9cbb1-118">В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.DataGridCell> элементы управления были объявлены с экрана, как «custom».</span><span class="sxs-lookup"><span data-stu-id="9cbb1-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="9cbb1-119">Начиная с платформы .NET Framework 4.7.1, они теперь правильно воспринимаются как (локализованный) ячейки сетки данных.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="9cbb1-120">Начиная с .NET Framework 4.7.1 чтения с экрана сообщать имя редактируемого <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="9cbb1-121">В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.PasswordBox> элементы управления были объявлены как «нет элемент в представлении» или бы в противном случае неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="9cbb1-122">Эта проблема исправлена, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="9cbb1-123">**Поддержка UIAutomation LiveRegion**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="9cbb1-124">Например, Экранный диктор для пользователей чтения с экрана содержимое пользовательского интерфейса приложения, обычно озвучивания текста вывод содержимого пользовательского интерфейса, который находится в фокусе.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="9cbb1-125">Тем не менее если элемент пользовательского интерфейса изменяется и не имеет фокуса, пользователь не может получать уведомления и пропустить важные сведения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="9cbb1-126">Динамическая областей стремятся решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="9cbb1-127">Разработчик может использовать их для информирования чтения с экрана или любым другим клиентом UIAutomation, важные изменения в элемент пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="9cbb1-128">Как и когда средства чтения с экрана можно настроить для оповещения пользователя этого изменения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="9cbb1-129">Для поддержки динамической областей, для WPF были добавлены следующие API:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="9cbb1-130"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> И <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> поля, которые идентифицируют **LiveSetting** свойство и **LiveRegionChanged** событий.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="9cbb1-131">Они могут быть заданы с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="9cbb1-132">**AutomationProperties.LiveSetting** вложенное свойство зависимостей, который уведомляет чтения с экрана важные изменения пользовательского интерфейса для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="9cbb1-133"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> Свойство, которое идентифицирует **AutomationProperties.LiveSetting** вложенное свойство.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="9cbb1-134"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> Метод, который может быть переопределен **LiveSetting** значение.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="9cbb1-135"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> И <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> методы get и set **LiveSetting** значение.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="9cbb1-136"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> Перечисления, который определяет следующие возможные **LiveSetting** значения:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="9cbb1-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9cbb1-138">Элемент не отправлять уведомления при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="9cbb1-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9cbb1-140">Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="9cbb1-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9cbb1-142">Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="9cbb1-143">Можно создать, задав LiveRegion **AutomationProperties.LiveSetting** свойство элемента, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="9cbb1-144">При изменении данных в области динамической и необходимо проинформировать чтения с экрана, можно явно вызвать событие, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="9cbb1-145">**Высокая контрастность**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-145">**High contrast**</span></span>

<span data-ttu-id="9cbb1-146">Начиная с платформы .NET Framework 4.7.1, в высокой контрастности внесены изменения для различных элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="9cbb1-147">Они будут отображаться при <xref:System.Windows.SystemParameters.HighContrast%2A> задана тема.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="9cbb1-148">К ним относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-148">These include:</span></span>

- <span data-ttu-id="9cbb1-149">Элемент управления <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="9cbb1-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="9cbb1-150">Фокус visual для <xref:System.Windows.Controls.Expander> теперь отображается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="9cbb1-151">Визуальные элементы клавиатуры для <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, и <xref:System.Windows.Controls.RadioButton> элементы управления также являются видимыми.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="9cbb1-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-152">For example:</span></span>

    <span data-ttu-id="9cbb1-153">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-153">Before:</span></span> 
    
    ![Элемент управления Expander с фокусом, прежде чем более удобным](media/expander-before.png)

    <span data-ttu-id="9cbb1-155">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-155">After:</span></span> 

    ![Элемент управления Expander с фокусом после более удобным](media/expander-after.png)

- <span data-ttu-id="9cbb1-157"><xref:System.Windows.Controls.CheckBox>и <xref:System.Windows.Controls.RadioButton> элементов управления</span><span class="sxs-lookup"><span data-stu-id="9cbb1-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="9cbb1-158">Текст в <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> элементы управления теперь стало проще см. При выборе режима высокой контрастности темы.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="9cbb1-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-159">For example:</span></span>

    <span data-ttu-id="9cbb1-160">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-160">Before:</span></span> 

    ![Высокая контрастность "переключатель" с фокусом, прежде чем более удобным](media/radio-button-before.png)
    
    <span data-ttu-id="9cbb1-162">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-162">After:</span></span> 

    ![Высокая контрастность "переключатель" с фокусом после более удобным](media/radio-button-after.png)

- <span data-ttu-id="9cbb1-164">Элемент управления <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="9cbb1-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="9cbb1-165">Начиная с .NET Framework 4.7.1, границы отключенного <xref:System.Windows.Controls.ComboBox> элемент управления является цвет отключенного текста.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="9cbb1-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-166">For example:</span></span>
    
    <span data-ttu-id="9cbb1-167">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-167">Before:</span></span> 

     ![Поле со списком отключено границей и текстом перед более удобным](media/combo-disabled-before.png)

    <span data-ttu-id="9cbb1-169">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-169">After:</span></span>   

     ![После более удобным ComboBox отключен границей и текстом](media/combo-disabled-after.png)

    <span data-ttu-id="9cbb1-171">Кроме того отключен и имеющего фокус кнопки использовать цвет правильный темы.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="9cbb1-172">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-172">Before:</span></span>

    ![Кнопка цвета темы до более удобным](media/button-themes-before.png) 
    
    <span data-ttu-id="9cbb1-174">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-174">After:</span></span> 

    ![Кнопка цвета темы после более удобным](media/button-themes-after.png) 

    <span data-ttu-id="9cbb1-176">Наконец, в .NET Framework 4.7 и более ранних версий, установка <xref:System.Windows.Controls.ComboBox> стиль элемента управления для `Toolbar.ComboBoxStyleKey` вызвала стрелку раскрывающегося списка, чтобы быть скрытым.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="9cbb1-177">Эта проблема исправлена, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="9cbb1-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-178">For example:</span></span>

    <span data-ttu-id="9cbb1-179">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey до более удобным](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="9cbb1-181">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey после более удобным](media/comboboxstylekey-after.png) 

- <span data-ttu-id="9cbb1-183">Элемент управления <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="9cbb1-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="9cbb1-184">Начиная с .NET Framework 4.7.1, стрелку индикатор сортировки в <xref:System.Windows.Controls.DataGrid> управляет теперь использует исправить цвета темы.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="9cbb1-185">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-185">For example:</span></span>

    <span data-ttu-id="9cbb1-186">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-186">Before:</span></span> 

    ![Индикатор стрелку сортировки до более удобным](media/sort-indicator-before.png) 
    
    <span data-ttu-id="9cbb1-188">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-188">After:</span></span>   
 
    ![Индикатор стрелку сортировки после более удобным](media/sort-indicator-after.png) 
    
    <span data-ttu-id="9cbb1-190">Кроме того в .NET Framework 4.7 и более ранних версий, стиль ссылки по умолчанию изменен на неверный цвет, мыши в режиме высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="9cbb1-191">Это разрешается, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="9cbb1-192">Аналогичным образом <xref:System.Windows.Controls.DataGrid> столбцы флажок использует ожидаемый цвета для отзывов фокус клавиатуры, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="9cbb1-193">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-193">Before:</span></span> 

    ![Стиль ссылки по умолчанию DataGrid до более удобным](media/default-link-style-before.png) 
 
    <span data-ttu-id="9cbb1-195">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-195">After:</span></span>    
  
    ![Стиль ссылки по умолчанию DataGrid после более удобным](media/default-link-style-after.png)  

<span data-ttu-id="9cbb1-197">Дополнительные сведения об улучшениях специальных возможностей WPF в платформе .NET Framework 4.7.1 см. в разделе [более удобным в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="9cbb1-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="9cbb1-198">Улучшения специальных возможностей Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9cbb1-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="9cbb1-199">В платформе .NET Framework 4.7.1 Windows Forms (WinForms) содержит специальные возможности изменения в следующих областях.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="9cbb1-200">**Улучшенное отображение в режиме высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="9cbb1-201">Начиная с .NET Framework 4.7.1 различные элементы управления WinForms обеспечивают улучшенную подготовки к просмотру в режимы Высокая контрастность, доступные в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="9cbb1-202">Windows 10 были изменены для некоторых системных цветов, высокая контрастность и Windows Forms основана на платформе Windows 10 Win32.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="9cbb1-203">Для получения наилучших результатов выполните самую последнюю версию Windows и выбрать последние изменения операционной системы, добавление в файл app.manifest в тестовое приложение и отменить преобразование в комментарий Windows 10 поддерживается ОС строки таким образом, следующее:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="9cbb1-204">Некоторые примеры изменения режима высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="9cbb1-205">Пометок в <xref:System.Windows.Forms.MenuStrip> элементов более удобны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="9cbb1-206">При выборе отключены <xref:System.Windows.Forms.MenuStrip> элементов более удобны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="9cbb1-207">Текст в выбранной <xref:System.Windows.Forms.Button> управления отличается от выбора цвета.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="9cbb1-208">Отключенного текста является более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-208">Disabled text is easier to read.</span></span> <span data-ttu-id="9cbb1-209">Пример:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-209">For example:</span></span>

    <span data-ttu-id="9cbb1-210">До:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-210">Before:</span></span>

    ![Отключенного текста до более удобным](media/wf-disabled-before.png) 

    <span data-ttu-id="9cbb1-212">После:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-212">After:</span></span>

    ![Отключенного текста после более удобным](media/wf-disabled-after.png) 

- <span data-ttu-id="9cbb1-214">Усовершенствования режима высокой контрастности в диалоговое окно исключения потока.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="9cbb1-215">**Улучшенная поддержка Экранный диктор**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-215">**Improved Narrator support**</span></span>

<span data-ttu-id="9cbb1-216">Windows Forms в .NET Framework 4.7.1 включает следующие улучшения специальных возможностей для Экранный диктор.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="9cbb1-217"><xref:System.Windows.Forms.MonthCalendar> Элемент управления может быть доступен Экранный диктор, а также с другими средствами автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="9cbb1-218"><xref:System.Windows.Forms.CheckedListBox> Управления оповещает Экранный диктор состояния флажка элемента изменился, и пользователь получает уведомление, что они изменили значение элемента списка.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="9cbb1-219"><xref:System.Windows.Forms.DataGridViewCell> Экранный диктор управления сообщает правильное состояние только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="9cbb1-220">Экранный диктор сможете прочитать отключено <xref:System.Windows.Forms.ToolStripMenuItem> текста, в то время как ранее он пропустить пунктов меню отключен.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="9cbb1-221">**Улучшенная поддержка шаблонов UIAutomation специальных возможностей**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="9cbb1-222">Начиная с платформы .NET Framework 4.7.1, разработчики средств специальных возможностей технологии могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="9cbb1-223">Эти улучшения специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="9cbb1-224"><xref:System.Windows.Forms.ComboBox> И <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон expand collapse](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="9cbb1-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="9cbb1-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> Теперь поддерживает [шаблон toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="9cbb1-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="9cbb1-226"><xref:System.Windows.Forms.ToolStripItem> Управления поддерживает <xref:System.Windows.Automation.AutomationElement.Name> свойство и [шаблон expand collapse](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="9cbb1-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="9cbb1-227"><xref:System.Windows.Forms.NumericUpDown> И <xref:System.Windows.Forms.DomainUpDown> элементы управления поддерживают <xref:System.Windows.Automation.automationElement.Name> свойство.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="9cbb1-228">**Свойство улучшенное взаимодействие с браузером**</span><span class="sxs-lookup"><span data-stu-id="9cbb1-228">**Improved property browser experience**</span></span>

<span data-ttu-id="9cbb1-229">Начиная с платформы .NET Framework 4.7.1, Windows Forms включает в себя:</span><span class="sxs-lookup"><span data-stu-id="9cbb1-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="9cbb1-230">Улучшения с помощью клавиатуры через различные окна выбора раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="9cbb1-231">Сокращение ненужных позицию табуляции.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="9cbb1-232">Улучшенные отчеты типов элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-232">Better reporting of control types.</span></span>
- <span data-ttu-id="9cbb1-233">Экранный диктор улучшенное поведение.</span><span class="sxs-lookup"><span data-stu-id="9cbb1-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="9cbb1-234">См. также</span><span class="sxs-lookup"><span data-stu-id="9cbb1-234">See Also</span></span>
[<span data-ttu-id="9cbb1-235">Новые возможности .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9cbb1-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 