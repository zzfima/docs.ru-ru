---
title: "Улучшения специальных возможностей в .NET Framework"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="196e6-102">Улучшения специальных возможностей в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="196e6-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="196e6-103">Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="196e6-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="196e6-104">Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="196e6-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="196e6-105">Начиная с .NET Framework 4.7.1, платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения.</span><span class="sxs-lookup"><span data-stu-id="196e6-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="196e6-106">Новые специальные возможности включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="196e6-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="196e6-107">Кроме того, приложения, которые ориентированы на более раннюю версию .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей в .NET Framework 4.7.1), добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="196e6-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="196e6-108">Аналогичным образом, приложения, ориентированные на версии .NET Framework, начиная с 4.7.1, могут отключить специальные возможности, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="196e6-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="196e6-109">Улучшения специальных возможностей в .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="196e6-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="196e6-110">.NET Framework 4.7.1 включает новые специальные возможности в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="196e6-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="196e6-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="196e6-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="196e6-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="196e6-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="196e6-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="196e6-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="196e6-114">**Улучшения средств чтения с экрана**</span><span class="sxs-lookup"><span data-stu-id="196e6-114">**Screen reader improvements**</span></span>

<span data-ttu-id="196e6-115">Если включены улучшения специальных возможностей, .NET Framework 4.7.1 содержит следующие усовершенствования, касающиеся средств чтения с экрана:</span><span class="sxs-lookup"><span data-stu-id="196e6-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="196e6-116">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.Expander> объявлялись средствами чтения с экрана как кнопки.</span><span class="sxs-lookup"><span data-stu-id="196e6-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="196e6-117">Начиная с .NET Framework 4.7.1, они правильно объявляются как развертываемые/свертываемые группы.</span><span class="sxs-lookup"><span data-stu-id="196e6-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="196e6-118">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.DataGridCell> объявлялись средствами чтения с экрана как настраиваемые.</span><span class="sxs-lookup"><span data-stu-id="196e6-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="196e6-119">Начиная с .NET Framework 4.7.1, они правильно объявляются как ячейка сетки данных (локализованная).</span><span class="sxs-lookup"><span data-stu-id="196e6-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="196e6-120">Начиная с .NET Framework 4.7.1, средства чтения с экрана объявляют имя изменяемого <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="196e6-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="196e6-121">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.PasswordBox> объявлялись как "в представлении нет элементов" или имели иное неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="196e6-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="196e6-122">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="196e6-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="196e6-123">**Поддержка динамических областей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="196e6-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="196e6-124">Средства чтения с экрана, такие как экранный диктор, помогают людям читать содержимое пользовательского интерфейса приложения. Обычно для этого используется преобразование текста в речь для содержимого, находящегося в фокусе.</span><span class="sxs-lookup"><span data-stu-id="196e6-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="196e6-125">Однако если элемент пользовательского интерфейса изменяется и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения.</span><span class="sxs-lookup"><span data-stu-id="196e6-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="196e6-126">Динамические области призваны решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="196e6-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="196e6-127">Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента автоматизации пользовательского интерфейса о важных изменениях элемента пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="196e6-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="196e6-128">После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="196e6-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="196e6-129">Для поддержки динамических областей в WPF добавлены следующие API:</span><span class="sxs-lookup"><span data-stu-id="196e6-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="196e6-130">Поля <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, которые идентифицируют свойство **LiveSetting** и событие **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="196e6-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="196e6-131">Их можно задать с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="196e6-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="196e6-132">Присоединенное свойство **AutomationProperties.LiveSetting**, средство чтения с экрана, уведомляющее о том, насколько важно изменение пользовательского интерфейса для пользователя.</span><span class="sxs-lookup"><span data-stu-id="196e6-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="196e6-133">Свойство<xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, которое идентифицирует присоединенное свойство **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="196e6-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="196e6-134">Метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, который можно переопределить для предоставления значения **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="196e6-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="196e6-135">Методы <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, которые возвращают и задают значение **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="196e6-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="196e6-136">Перечисление <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, которое определяет следующие возможные значения **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="196e6-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="196e6-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="196e6-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="196e6-138">Элемент не отправляет уведомления при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="196e6-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="196e6-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="196e6-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="196e6-140">Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="196e6-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="196e6-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="196e6-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="196e6-142">Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="196e6-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="196e6-143">Вы можете создать динамическую область, задав свойство **AutomationProperties.LiveSetting** для нужного элемента, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="196e6-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="196e6-144">Когда данные в динамической области изменяются и вам нужно проинформировать средство чтения с экрана, можно явно вызвать событие, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="196e6-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="196e6-145">**Высокая контрастность**</span><span class="sxs-lookup"><span data-stu-id="196e6-145">**High contrast**</span></span>

<span data-ttu-id="196e6-146">Начиная с .NET Framework 4.7.1, внесены улучшения в функции высокой контрастности для различных элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="196e6-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="196e6-147">Теперь они видны, когда задана тема <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="196e6-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="196e6-148">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="196e6-148">These include:</span></span>

- <span data-ttu-id="196e6-149">Элемент управления <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="196e6-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="196e6-150">Визуальный элемент фокуса для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается.</span><span class="sxs-lookup"><span data-stu-id="196e6-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="196e6-151">Визуальные элементы клавиатуры для элементов управления <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.RadioButton> также видимы.</span><span class="sxs-lookup"><span data-stu-id="196e6-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="196e6-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-152">For example:</span></span>

    <span data-ttu-id="196e6-153">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-153">Before:</span></span> 
    
    ![Элемент управления Expander с фокусом до внесения улучшений](media/expander-before.png)

    <span data-ttu-id="196e6-155">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-155">After:</span></span> 

    ![Элемент управления Expander с фокусом после внесения улучшений](media/expander-after.png)

- <span data-ttu-id="196e6-157">Элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="196e6-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="196e6-158">Текст в элементах управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> теперь стало проще читать, когда он выбран при использовании тем с высокой контрастностью.</span><span class="sxs-lookup"><span data-stu-id="196e6-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="196e6-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-159">For example:</span></span>

    <span data-ttu-id="196e6-160">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-160">Before:</span></span> 

    ![Переключатель высокой контрастности до внесения улучшений](media/radio-button-before.png)
    
    <span data-ttu-id="196e6-162">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-162">After:</span></span> 

    ![Переключатель высокой контрастности после внесения улучшений](media/radio-button-after.png)

- <span data-ttu-id="196e6-164">Элемент управления <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="196e6-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="196e6-165">Начиная с .NET Framework 4.7.1, граница отключенного элемента управления <xref:System.Windows.Controls.ComboBox> имеет цвет отключенного текста.</span><span class="sxs-lookup"><span data-stu-id="196e6-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="196e6-166">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-166">For example:</span></span>
    
    <span data-ttu-id="196e6-167">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-167">Before:</span></span> 

     ![Отключенная граница и текст поля со списком до внесения улучшений](media/combo-disabled-before.png)

    <span data-ttu-id="196e6-169">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-169">After:</span></span>   

     ![Отключенная граница и текст поля со списком после внесения улучшений](media/combo-disabled-after.png)

    <span data-ttu-id="196e6-171">Кроме того, отключенные и находящиеся в фокусе кнопки используют правильный цвет темы.</span><span class="sxs-lookup"><span data-stu-id="196e6-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="196e6-172">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-172">Before:</span></span>

    ![Цвета темы для кнопок до внесения улучшений](media/button-themes-before.png) 
    
    <span data-ttu-id="196e6-174">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-174">After:</span></span> 

    ![Цвета темы для кнопок после внесения улучшений](media/button-themes-after.png) 

    <span data-ttu-id="196e6-176">Наконец, в .NET Framework 4.7 и более ранних версий установка стиля элемента управления <xref:System.Windows.Controls.ComboBox> в значение `Toolbar.ComboBoxStyleKey` приводила к тому, что стрелка раскрывающегося списка была невидимой.</span><span class="sxs-lookup"><span data-stu-id="196e6-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="196e6-177">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="196e6-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="196e6-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-178">For example:</span></span>

    <span data-ttu-id="196e6-179">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey до внесения улучшений](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="196e6-181">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey после внесения улучшений](media/comboboxstylekey-after.png) 

- <span data-ttu-id="196e6-183">Элемент управления <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="196e6-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="196e6-184">Начиная с .NET Framework 4.7.1, стрелка индикатора сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> теперь использует правильные цвета темы.</span><span class="sxs-lookup"><span data-stu-id="196e6-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="196e6-185">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-185">For example:</span></span>

    <span data-ttu-id="196e6-186">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-186">Before:</span></span> 

    ![Стрелка индикатора сортировки до внесения улучшений](media/sort-indicator-before.png) 
    
    <span data-ttu-id="196e6-188">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-188">After:</span></span>   
 
    ![Стрелка индикатора сортировки после внесения улучшений](media/sort-indicator-after.png) 
    
    <span data-ttu-id="196e6-190">Кроме того, в .NET Framework 4.7 и более ранних версий стиль ссылки по умолчанию изменялся на неправильный цвет при наведении указателя мыши в режимах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="196e6-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="196e6-191">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="196e6-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="196e6-192">Аналогичным образом, столбец флажка <xref:System.Windows.Controls.DataGrid> использует ожидаемые цвета для отзывов на фокус клавиатуры, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="196e6-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="196e6-193">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-193">Before:</span></span> 

    ![Стиль ссылки по умолчанию DataGrid до внесения улучшений](media/default-link-style-before.png) 
 
    <span data-ttu-id="196e6-195">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-195">After:</span></span>    
  
    ![Стиль ссылки по умолчанию DataGrid после внесения улучшений](media/default-link-style-after.png)  

<span data-ttu-id="196e6-197">Дополнительные сведения об улучшениях специальных возможностей WPF в .NET Framework 4.7.1 см. в разделе [Улучшения специальных возможностей в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="196e6-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="196e6-198">Улучшения специальных возможностей в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="196e6-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="196e6-199">В компонент Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="196e6-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="196e6-200">**Улучшенное отображение в режиме высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="196e6-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="196e6-201">Начиная с .NET Framework 4.7.1, различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="196e6-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="196e6-202">В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="196e6-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="196e6-203">Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:</span><span class="sxs-lookup"><span data-stu-id="196e6-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="196e6-204">Некоторые примеры изменения режима высокой контрастности:</span><span class="sxs-lookup"><span data-stu-id="196e6-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="196e6-205">Лучше читаются флажки в элементах <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="196e6-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="196e6-206">Лучше читаются выбранные отключенные элементы <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="196e6-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="196e6-207">Текст в выбранном <xref:System.Windows.Forms.Button> элементе управления отличается от цвета выбора.</span><span class="sxs-lookup"><span data-stu-id="196e6-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="196e6-208">Отключенный текст проще читать.</span><span class="sxs-lookup"><span data-stu-id="196e6-208">Disabled text is easier to read.</span></span> <span data-ttu-id="196e6-209">Пример:</span><span class="sxs-lookup"><span data-stu-id="196e6-209">For example:</span></span>

    <span data-ttu-id="196e6-210">До:</span><span class="sxs-lookup"><span data-stu-id="196e6-210">Before:</span></span>

    ![Отключенный текст до внесения улучшений](media/wf-disabled-before.png) 

    <span data-ttu-id="196e6-212">После:</span><span class="sxs-lookup"><span data-stu-id="196e6-212">After:</span></span>

    ![Отключенный текст после внесения улучшений](media/wf-disabled-after.png) 

- <span data-ttu-id="196e6-214">Усовершенствования режима высокой контрастности в диалоговом окне исключения потока.</span><span class="sxs-lookup"><span data-stu-id="196e6-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="196e6-215">**Улучшенная поддержка экранного диктора**</span><span class="sxs-lookup"><span data-stu-id="196e6-215">**Improved Narrator support**</span></span>

<span data-ttu-id="196e6-216">Компонент Windows Forms в .NET Framework 4.7.1 содержит следующие улучшения специальных возможностей для экранного диктора:</span><span class="sxs-lookup"><span data-stu-id="196e6-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="196e6-217">К элементу управления <xref:System.Windows.Forms.MonthCalendar> может обратиться как экранный диктор, так и любое другое средство автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="196e6-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="196e6-218">Элемент управления <xref:System.Windows.Forms.CheckedListBox> оповещает экранный диктор об изменении состояния флажка элемента, чтобы пользователь узнал, что значение элемента списка изменилось.</span><span class="sxs-lookup"><span data-stu-id="196e6-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="196e6-219">Элемент управления <xref:System.Windows.Forms.DataGridViewCell> сообщает правильное состояние доступа только для чтения экранному диктору.</span><span class="sxs-lookup"><span data-stu-id="196e6-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="196e6-220">Теперь экранный диктор может прочитать отключенный текст <xref:System.Windows.Forms.ToolStripMenuItem>, хотя раньше он пропускал отключенные пункты меню.</span><span class="sxs-lookup"><span data-stu-id="196e6-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="196e6-221">**Улучшенная поддержка шаблонов специальных возможностей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="196e6-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="196e6-222">Начиная с .NET Framework 4.7.1, разработчики средств специальных возможностей могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms.</span><span class="sxs-lookup"><span data-stu-id="196e6-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="196e6-223">Некоторые из этих улучшений специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="196e6-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="196e6-224"><xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="196e6-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="196e6-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> теперь поддерживает [шаблон переключения](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="196e6-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="196e6-226">Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="196e6-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="196e6-227">Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="196e6-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="196e6-228">**Улучшенное взаимодействие с обозревателем свойств**</span><span class="sxs-lookup"><span data-stu-id="196e6-228">**Improved property browser experience**</span></span>

<span data-ttu-id="196e6-229">Начиная с .NET Framework 4.7.1, компонент Windows Forms включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="196e6-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="196e6-230">Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.</span><span class="sxs-lookup"><span data-stu-id="196e6-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="196e6-231">Сокращение ненужных позиций табуляции.</span><span class="sxs-lookup"><span data-stu-id="196e6-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="196e6-232">Улучшенные отчеты о типах элементов управления.</span><span class="sxs-lookup"><span data-stu-id="196e6-232">Better reporting of control types.</span></span>
- <span data-ttu-id="196e6-233">Улучшенная работа экранного диктора.</span><span class="sxs-lookup"><span data-stu-id="196e6-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="196e6-234">См. также</span><span class="sxs-lookup"><span data-stu-id="196e6-234">See Also</span></span>
[<span data-ttu-id="196e6-235">Новые возможности .NET Framework</span><span class="sxs-lookup"><span data-stu-id="196e6-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 