---
title: Улучшения специальных возможностей в .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 092b1cfc9350ea398eb18199f19a8eee7ea9f218
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675443"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="43995-102">Улучшения специальных возможностей в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="43995-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="43995-103">Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="43995-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="43995-104">Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="43995-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="43995-105">Начиная с .NET Framework 4.7.1, платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения.</span><span class="sxs-lookup"><span data-stu-id="43995-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

## <a name="accessibility-switches"></a><span data-ttu-id="43995-106">Переключатель специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="43995-106">Accessibility switches</span></span>

<span data-ttu-id="43995-107">Вы можете включить в приложении функции специальных возможностей, если оно предназначено для .NET Framework 4.7 или более ранней версии, но выполняется на платформе .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="43995-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="43995-108">Вы также можете настроить в приложении использование компонентов прежних версий (и не использовать преимущества функций специальных возможностей), если оно предназначен для .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="43995-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="43995-109">У каждой версии платформы .NET Framework с функциями специальных возможностей есть специальный переключатель, который можно добавить в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="43995-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="43995-110">Ниже приведены поддерживаемые переключатели:</span><span class="sxs-lookup"><span data-stu-id="43995-110">The following are the supported switches:</span></span>

|<span data-ttu-id="43995-111">Версия</span><span class="sxs-lookup"><span data-stu-id="43995-111">Version</span></span>|<span data-ttu-id="43995-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="43995-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="43995-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="43995-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="43995-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="43995-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="43995-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="43995-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="43995-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="43995-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="43995-117">Использование преимуществ усовершенствованных специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="43995-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="43995-118">Новые специальные возможности включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="43995-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="43995-119">Кроме того, приложения, которые ориентированы на более раннюю версию .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей). Для этого добавьте следующие переключатели в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установите для них значение `false`.</span><span class="sxs-lookup"><span data-stu-id="43995-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="43995-120">В следующем примере показано, как принять усовершенствованные специальные возможности, представленные в .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="43995-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="43995-121">Если вы решили включить функции специальных возможностей из более поздней версии .NET Framework, необходимо явным образом включить эти функции из более ранних версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43995-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="43995-122">Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1 и 4.7.2 требуется следующий элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span><span class="sxs-lookup"><span data-stu-id="43995-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="43995-123">Восстановление поведения из предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="43995-123">Restoring legacy behavior</span></span>

<span data-ttu-id="43995-124">Для приложений, ориентированных на версии .NET Framework, начиная с 4.7.1, можно отключить функции специальных возможностей, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установив значение `true`.</span><span class="sxs-lookup"><span data-stu-id="43995-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="43995-125">Например, следующая конфигурация задает отказ от функций специальных возможностей, представленных в .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="43995-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="43995-126">Улучшения специальных возможностей в .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="43995-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="43995-127">.NET Framework 4.7.2 включает новые функции специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="43995-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="43995-128">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43995-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="43995-129">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="43995-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a><span data-ttu-id="43995-130">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43995-130">Windows Forms</span></span>

<span data-ttu-id="43995-131">**Определенные в ОС цвета в темах высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="43995-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="43995-132">Начиная с .NET Framework 4.7.2 Windows Forms использует цвета, определенные в операционной системе, в темах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="43995-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="43995-133">Это влияет на следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="43995-133">This affects the following controls:</span></span>

- <span data-ttu-id="43995-134">Стрелка раскрывающегося списка элемента управления <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="43995-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="43995-135">Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox>, у которых для параметра <xref:System.Windows.Forms.ButtonBase.FlatStyle> установлено значение <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> или <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43995-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43995-136">Ранее выбранные цвета текста и фона не были контрастными и текст было сложно читать.</span><span class="sxs-lookup"><span data-stu-id="43995-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="43995-137">Элементы управления, содержащиеся в <xref:System.Windows.Forms.GroupBox>, у которого для свойства <xref:System.Windows.Forms.Control.Enabled> установлено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="43995-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
 
- <span data-ttu-id="43995-138">Элементы управления <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> и <xref:System.Windows.Forms.ToolStripDropDownButton>, которые имеют повышенное значение контрастности яркости в режиме высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="43995-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="43995-139">Свойство <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> класса <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="43995-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="43995-140">**Усовершенствования экранного диктора**</span><span class="sxs-lookup"><span data-stu-id="43995-140">**Narrator improvements**</span></span>

<span data-ttu-id="43995-141">Начиная с .NET Framework 4.7.2 усовершенствована поддержка экранного диктора:</span><span class="sxs-lookup"><span data-stu-id="43995-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="43995-142">Он сообщает значение свойства <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> при объявлении текста <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="43995-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span> 

- <span data-ttu-id="43995-143">Он указывает, когда для свойства <xref:System.Windows.Forms.Control.Enabled> элемента <xref:System.Windows.Forms.ToolStripMenuItem> задано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="43995-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="43995-144">Он предоставляет отзыв о состоянии флажка, если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="43995-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="43995-145">Порядок фокуса экранного диктора в режиме сканирования согласуется с визуальным порядком элементов управления в диалоговом окне загрузки ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="43995-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="43995-146">**Усовершенствования DataGridView**</span><span class="sxs-lookup"><span data-stu-id="43995-146">**DataGridView improvements**</span></span>

<span data-ttu-id="43995-147">Начиная с .NET Framework 4.7.2 элемент управления <xref:System.Windows.Forms.DataGridView> вносит следующие улучшения специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="43995-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="43995-148">Строки можно сортировать с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="43995-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="43995-149">Пользователь может нажать клавишу F3, чтобы выполнить сортировку по текущему столбцу.</span><span class="sxs-lookup"><span data-stu-id="43995-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="43995-150">Когда <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, заголовок столбца меняет цвет для указания на текущий столбец, когда пользователь переходит по ячейкам в текущей строке.</span><span class="sxs-lookup"><span data-stu-id="43995-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="43995-151">Свойство <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> возвращает правильный родительский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="43995-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="43995-152">**Улучшенные визуальные подсказки**</span><span class="sxs-lookup"><span data-stu-id="43995-152">**Improved visual cues**</span></span>

- <span data-ttu-id="43995-153">Элементы управления <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox> с пустым свойством <xref:System.Windows.Forms.ButtonBase.Text> отображают индикатор фокуса при получении фокуса.</span><span class="sxs-lookup"><span data-stu-id="43995-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="43995-154">**Улучшенная поддержка сетки свойств**</span><span class="sxs-lookup"><span data-stu-id="43995-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="43995-155">Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> теперь возвращают `true` для <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> свойства только в том случае, если включен элемент PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="43995-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="43995-156">Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> возвращают `false` для свойства <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> только в том случае, если элемент PropertyGrid может быть изменен пользователем.</span><span class="sxs-lookup"><span data-stu-id="43995-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="43995-157">**Улучшение навигации с помощью клавиатуры**</span><span class="sxs-lookup"><span data-stu-id="43995-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="43995-158">Элемент управления <xref:System.Windows.Forms.ToolStripButton> позволяет отображать фокус, если он содержится в <xref:System.Windows.Forms.ToolStripPanel>, для свойства <xref:System.Windows.Forms.ToolStripPanel.TabStop> которого задано значение `true`</span><span class="sxs-lookup"><span data-stu-id="43995-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="43995-159">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="43995-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="43995-160">**Изменения элементов управления CheckBox и RadioButton**</span><span class="sxs-lookup"><span data-stu-id="43995-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="43995-161">В .NET Framework 4.7.1 и более ранних версий элементы управления <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> и <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> WPF имеют несогласованные и (в классической теме и теме высокой контрастности) неправильные визуальные элементы фокуса.</span><span class="sxs-lookup"><span data-stu-id="43995-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="43995-162">Это происходит в случаях, когда для элементов управления не задано какое-либо содержимое.</span><span class="sxs-lookup"><span data-stu-id="43995-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="43995-163">Это может затруднять переход между темами и отображение визуального элемента фокуса.</span><span class="sxs-lookup"><span data-stu-id="43995-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="43995-164">В .NET Framework 4.7.2 эти визуальные элементы стали более согласованными в разных темах и более видимыми в классической и контрастной темах.</span><span class="sxs-lookup"><span data-stu-id="43995-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="43995-165">**Элементы управления WinForms, размещенные в приложении WPF**</span><span class="sxs-lookup"><span data-stu-id="43995-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="43995-166">При использовании элемента управления WinForms, размещенного в приложении WPF в .NET Framework 4.7.1 и более ранних версий, пользователи не могли выйти из слоя WinForms с помощью клавиши табуляции, если первый или последний элемент управления в слое был элементом управления <xref:System.Windows.Forms.Integration.ElementHost> WPF.</span><span class="sxs-lookup"><span data-stu-id="43995-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="43995-167">В .NET Framework 4.7.2 пользователи теперь могут выйти из слоя WinForms с помощью клавиши табуляции.</span><span class="sxs-lookup"><span data-stu-id="43995-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="43995-168">Однако автоматизированные приложения, которые зависят от постоянного нахождения фокуса в слое WinForms, могут работать некорректно.</span><span class="sxs-lookup"><span data-stu-id="43995-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="43995-169">Улучшения специальных возможностей в .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="43995-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="43995-170">.NET Framework 4.7.1 включает новые специальные возможности в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="43995-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="43995-171">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="43995-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="43995-172">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43995-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="43995-173">Веб-элементы управления ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43995-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="43995-174">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="43995-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="43995-175">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="43995-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>
### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="43995-176">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="43995-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="43995-177">**Улучшения средств чтения с экрана**</span><span class="sxs-lookup"><span data-stu-id="43995-177">**Screen reader improvements**</span></span>

<span data-ttu-id="43995-178">Если включены улучшения специальных возможностей, .NET Framework 4.7.1 содержит следующие усовершенствования, касающиеся средств чтения с экрана:</span><span class="sxs-lookup"><span data-stu-id="43995-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="43995-179">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.Expander> объявлялись средствами чтения с экрана как кнопки.</span><span class="sxs-lookup"><span data-stu-id="43995-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="43995-180">Начиная с .NET Framework 4.7.1, они правильно объявляются как развертываемые/свертываемые группы.</span><span class="sxs-lookup"><span data-stu-id="43995-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="43995-181">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.DataGridCell> объявлялись средствами чтения с экрана как настраиваемые.</span><span class="sxs-lookup"><span data-stu-id="43995-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="43995-182">Начиная с .NET Framework 4.7.1, они правильно объявляются как ячейка сетки данных (локализованная).</span><span class="sxs-lookup"><span data-stu-id="43995-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="43995-183">Начиная с .NET Framework 4.7.1, средства чтения с экрана объявляют имя изменяемого <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="43995-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="43995-184">В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.PasswordBox> объявлялись как "в представлении нет элементов" или имели иное неправильное поведение.</span><span class="sxs-lookup"><span data-stu-id="43995-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="43995-185">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="43995-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="43995-186">**Поддержка динамических областей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="43995-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="43995-187">Средства чтения с экрана, такие как экранный диктор, помогают людям читать содержимое пользовательского интерфейса приложения. Обычно для этого используется преобразование текста в речь для содержимого, находящегося в фокусе.</span><span class="sxs-lookup"><span data-stu-id="43995-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="43995-188">Однако если элемент пользовательского интерфейса изменяется и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения.</span><span class="sxs-lookup"><span data-stu-id="43995-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="43995-189">Динамические области призваны решить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="43995-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="43995-190">Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента автоматизации пользовательского интерфейса о важных изменениях элемента пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43995-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="43995-191">После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="43995-191">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="43995-192">Для поддержки динамических областей в WPF добавлены следующие API:</span><span class="sxs-lookup"><span data-stu-id="43995-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="43995-193">Поля <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, которые идентифицируют свойство **LiveSetting** и событие **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="43995-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="43995-194">Их можно задать с помощью XAML.</span><span class="sxs-lookup"><span data-stu-id="43995-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="43995-195">Присоединенное свойство **AutomationProperties.LiveSetting**, уведомляющее средство чтения с экрана о том, насколько важно изменение пользовательского интерфейса для пользователя.</span><span class="sxs-lookup"><span data-stu-id="43995-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="43995-196">Свойство<xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, которое идентифицирует присоединенное свойство **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="43995-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="43995-197">Метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, который можно переопределить для предоставления значения **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="43995-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="43995-198">Методы <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, которые возвращают и задают значение **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="43995-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="43995-199">Перечисление <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, которое определяет следующие возможные значения **LiveSetting**:</span><span class="sxs-lookup"><span data-stu-id="43995-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="43995-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43995-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43995-201">Элемент не отправляет уведомления при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="43995-201">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="43995-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43995-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43995-203">Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="43995-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="43995-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43995-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="43995-205">Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.</span><span class="sxs-lookup"><span data-stu-id="43995-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="43995-206">Вы можете создать динамическую область, задав свойство **AutomationProperties.LiveSetting** для нужного элемента, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="43995-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="43995-207">Когда данные в динамической области изменяются и вам нужно проинформировать средство чтения с экрана, можно явно вызвать событие, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43995-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="43995-208">**Высокая контрастность**</span><span class="sxs-lookup"><span data-stu-id="43995-208">**High contrast**</span></span>

<span data-ttu-id="43995-209">Начиная с .NET Framework 4.7.1, внесены улучшения в функции высокой контрастности для различных элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="43995-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="43995-210">Теперь они видны, когда задана тема <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="43995-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="43995-211">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="43995-211">These include:</span></span>

- <span data-ttu-id="43995-212">Элемент управления <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="43995-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="43995-213">Визуальный элемент фокуса для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается.</span><span class="sxs-lookup"><span data-stu-id="43995-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="43995-214">Визуальные элементы клавиатуры для элементов управления <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.RadioButton> также видимы.</span><span class="sxs-lookup"><span data-stu-id="43995-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="43995-215">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-215">For example:</span></span>

    <span data-ttu-id="43995-216">До:</span><span class="sxs-lookup"><span data-stu-id="43995-216">Before:</span></span> 
    
    ![Элемент управления Expander с фокусом до внесения улучшений](media/expander-before.png)

    <span data-ttu-id="43995-218">После:</span><span class="sxs-lookup"><span data-stu-id="43995-218">After:</span></span> 

    ![Элемент управления Expander с фокусом после внесения улучшений](media/expander-after.png)

- <span data-ttu-id="43995-220">Элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="43995-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="43995-221">Текст в элементах управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> теперь стало проще читать, когда он выбран при использовании тем с высокой контрастностью.</span><span class="sxs-lookup"><span data-stu-id="43995-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="43995-222">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-222">For example:</span></span>

    <span data-ttu-id="43995-223">До:</span><span class="sxs-lookup"><span data-stu-id="43995-223">Before:</span></span> 

    ![Переключатель высокой контрастности до внесения улучшений](media/radio-button-before.png)
    
    <span data-ttu-id="43995-225">После:</span><span class="sxs-lookup"><span data-stu-id="43995-225">After:</span></span> 

    ![Переключатель высокой контрастности после внесения улучшений](media/radio-button-after.png)

- <span data-ttu-id="43995-227">Элемент управления <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="43995-227"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="43995-228">Начиная с .NET Framework 4.7.1, граница отключенного элемента управления <xref:System.Windows.Controls.ComboBox> имеет цвет отключенного текста.</span><span class="sxs-lookup"><span data-stu-id="43995-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="43995-229">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-229">For example:</span></span>
    
    <span data-ttu-id="43995-230">До:</span><span class="sxs-lookup"><span data-stu-id="43995-230">Before:</span></span> 

     ![Отключенная граница и текст поля со списком до внесения улучшений](media/combo-disabled-before.png)

    <span data-ttu-id="43995-232">После:</span><span class="sxs-lookup"><span data-stu-id="43995-232">After:</span></span>   

     ![Отключенная граница и текст поля со списком после внесения улучшений](media/combo-disabled-after.png)

    <span data-ttu-id="43995-234">Кроме того, отключенные и находящиеся в фокусе кнопки используют правильный цвет темы.</span><span class="sxs-lookup"><span data-stu-id="43995-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="43995-235">До:</span><span class="sxs-lookup"><span data-stu-id="43995-235">Before:</span></span>

    ![Цвета темы для кнопок до внесения улучшений](media/button-themes-before.png) 
    
    <span data-ttu-id="43995-237">После:</span><span class="sxs-lookup"><span data-stu-id="43995-237">After:</span></span> 

    ![Цвета темы для кнопок после внесения улучшений](media/button-themes-after.png) 

    <span data-ttu-id="43995-239">Наконец, в .NET Framework 4.7 и более ранних версий установка стиля элемента управления <xref:System.Windows.Controls.ComboBox> в значение `Toolbar.ComboBoxStyleKey` приводила к тому, что стрелка раскрывающегося списка была невидимой.</span><span class="sxs-lookup"><span data-stu-id="43995-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="43995-240">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="43995-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="43995-241">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-241">For example:</span></span>

    <span data-ttu-id="43995-242">До:</span><span class="sxs-lookup"><span data-stu-id="43995-242">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey до внесения улучшений](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="43995-244">После:</span><span class="sxs-lookup"><span data-stu-id="43995-244">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey после внесения улучшений](media/comboboxstylekey-after.png) 

- <span data-ttu-id="43995-246">Элемент управления <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="43995-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="43995-247">Начиная с .NET Framework 4.7.1, стрелка индикатора сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> теперь использует правильные цвета темы.</span><span class="sxs-lookup"><span data-stu-id="43995-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="43995-248">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-248">For example:</span></span>

    <span data-ttu-id="43995-249">До:</span><span class="sxs-lookup"><span data-stu-id="43995-249">Before:</span></span> 

    ![Стрелка индикатора сортировки до внесения улучшений](media/sort-indicator-before.png) 
    
    <span data-ttu-id="43995-251">После:</span><span class="sxs-lookup"><span data-stu-id="43995-251">After:</span></span>   
 
    ![Стрелка индикатора сортировки после внесения улучшений](media/sort-indicator-after.png) 
    
    <span data-ttu-id="43995-253">Кроме того, в .NET Framework 4.7 и более ранних версий стиль ссылки по умолчанию изменялся на неправильный цвет при наведении указателя мыши в режимах высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="43995-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="43995-254">Начиная с .NET Framework 4.7.1, эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="43995-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="43995-255">Аналогичным образом, столбец флажка <xref:System.Windows.Controls.DataGrid> использует ожидаемые цвета для отзывов на фокус клавиатуры, начиная с .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="43995-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="43995-256">До:</span><span class="sxs-lookup"><span data-stu-id="43995-256">Before:</span></span> 

    ![Стиль ссылки по умолчанию DataGrid до внесения улучшений](media/default-link-style-before.png) 
 
    <span data-ttu-id="43995-258">После:</span><span class="sxs-lookup"><span data-stu-id="43995-258">After:</span></span>    
  
    ![Стиль ссылки по умолчанию DataGrid после внесения улучшений](media/default-link-style-after.png)  

<span data-ttu-id="43995-260">Дополнительные сведения об улучшениях специальных возможностей WPF в .NET Framework 4.7.1 см. в разделе [Улучшения специальных возможностей в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="43995-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>
### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="43995-261">Улучшения специальных возможностей в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43995-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="43995-262">В компонент Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="43995-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="43995-263">**Улучшенное отображение в режиме высокой контрастности**</span><span class="sxs-lookup"><span data-stu-id="43995-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="43995-264">Начиная с .NET Framework 4.7.1 различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="43995-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="43995-265">В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="43995-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="43995-266">Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43995-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="43995-267">Некоторые примеры изменения режима высокой контрастности:</span><span class="sxs-lookup"><span data-stu-id="43995-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="43995-268">Лучше читаются флажки в элементах <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="43995-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="43995-269">Лучше читаются выбранные отключенные элементы <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="43995-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="43995-270">Текст в выбранном <xref:System.Windows.Forms.Button> элементе управления отличается от цвета выбора.</span><span class="sxs-lookup"><span data-stu-id="43995-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="43995-271">Отключенный текст проще читать.</span><span class="sxs-lookup"><span data-stu-id="43995-271">Disabled text is easier to read.</span></span> <span data-ttu-id="43995-272">Например:</span><span class="sxs-lookup"><span data-stu-id="43995-272">For example:</span></span>

    <span data-ttu-id="43995-273">До:</span><span class="sxs-lookup"><span data-stu-id="43995-273">Before:</span></span>

    ![Отключенный текст до внесения улучшений](media/wf-disabled-before.png) 

    <span data-ttu-id="43995-275">После:</span><span class="sxs-lookup"><span data-stu-id="43995-275">After:</span></span>

    ![Отключенный текст после внесения улучшений](media/wf-disabled-after.png) 

- <span data-ttu-id="43995-277">Усовершенствования режима высокой контрастности в диалоговом окне исключения потока.</span><span class="sxs-lookup"><span data-stu-id="43995-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="43995-278">**Улучшенная поддержка экранного диктора**</span><span class="sxs-lookup"><span data-stu-id="43995-278">**Improved Narrator support**</span></span>

<span data-ttu-id="43995-279">Компонент Windows Forms в .NET Framework 4.7.1 содержит следующие улучшения специальных возможностей для экранного диктора:</span><span class="sxs-lookup"><span data-stu-id="43995-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="43995-280">К элементу управления <xref:System.Windows.Forms.MonthCalendar> может обратиться как экранный диктор, так и любое другое средство автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43995-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="43995-281">Элемент управления <xref:System.Windows.Forms.CheckedListBox> оповещает экранный диктор об изменении состояния флажка элемента, чтобы пользователь узнал, что значение элемента списка изменилось.</span><span class="sxs-lookup"><span data-stu-id="43995-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="43995-282">Элемент управления <xref:System.Windows.Forms.DataGridViewCell> сообщает правильное состояние доступа только для чтения экранному диктору.</span><span class="sxs-lookup"><span data-stu-id="43995-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="43995-283">Теперь экранный диктор может прочитать отключенный текст <xref:System.Windows.Forms.ToolStripMenuItem>, хотя раньше он пропускал отключенные пункты меню.</span><span class="sxs-lookup"><span data-stu-id="43995-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="43995-284">**Улучшенная поддержка шаблонов специальных возможностей автоматизации пользовательского интерфейса**</span><span class="sxs-lookup"><span data-stu-id="43995-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="43995-285">Начиная с .NET Framework 4.7.1, разработчики средств специальных возможностей могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms.</span><span class="sxs-lookup"><span data-stu-id="43995-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="43995-286">Некоторые из этих улучшений специальных возможностей:</span><span class="sxs-lookup"><span data-stu-id="43995-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="43995-287"><xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="43995-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="43995-288"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> теперь поддерживает [шаблон переключения](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="43995-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="43995-289">Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="43995-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="43995-290">Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="43995-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="43995-291">**Улучшенное взаимодействие с обозревателем свойств**</span><span class="sxs-lookup"><span data-stu-id="43995-291">**Improved property browser experience**</span></span>

<span data-ttu-id="43995-292">Начиная с .NET Framework 4.7.1, компонент Windows Forms включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="43995-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="43995-293">Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.</span><span class="sxs-lookup"><span data-stu-id="43995-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="43995-294">Сокращение ненужных позиций табуляции.</span><span class="sxs-lookup"><span data-stu-id="43995-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="43995-295">Улучшенные отчеты о типах элементов управления.</span><span class="sxs-lookup"><span data-stu-id="43995-295">Better reporting of control types.</span></span>
- <span data-ttu-id="43995-296">Улучшенная работа экранного диктора.</span><span class="sxs-lookup"><span data-stu-id="43995-296">Improved narrator behavior.</span></span>
 
<a name="aspnet471"></a>
### <a name="aspnet-web-controls"></a><span data-ttu-id="43995-297">Веб-элементы управления ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43995-297">ASP.NET web controls</span></span>

<span data-ttu-id="43995-298">Начиная с .NET Framework 4.7.1 и Visual Studio 2017 15.3 в ASP.NET улучшена работа веб-элементов управления ASP.NET с технологией специальных возможностей в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43995-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="43995-299">Внесены следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="43995-299">Changes include the following:</span></span>

- <span data-ttu-id="43995-300">Изменения для реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления, например в диалоговом окне **Добавить поле** в мастере **представления сведений** или в диалоговом окне **Настройка ListView** в мастере **ListView**.</span><span class="sxs-lookup"><span data-stu-id="43995-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="43995-301">Изменения для улучшенного отображения в режиме высокой контрастности, например в **редакторе полей страничного навигатора данных**.</span><span class="sxs-lookup"><span data-stu-id="43995-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="43995-302">Изменения для улучшения навигации с помощью клавиатуры для таких элементов, как диалоговое окно **Поля** в мастере **полей страничного навигатора**, диалоговое окно **Настроить ObjectContext** или **Настроить выбор данных** в мастере **настройки источника данных**.</span><span class="sxs-lookup"><span data-stu-id="43995-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>
### <a name="net-sdk-tools"></a><span data-ttu-id="43995-303">.NET SDK Tools</span><span class="sxs-lookup"><span data-stu-id="43995-303">.NET SDK Tools</span></span>

<span data-ttu-id="43995-304">В [редакторе конфигурации (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) и [средстве Service Trace Viewer (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) были устранены различные ошибки специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="43995-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="43995-305">В основном это были незначительные проблемы, например не определялось имя или некорректно реализовывались шаблоны автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43995-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="43995-306">Многие пользователи могли не замечать неверные значения, но пользователям, использующим вспомогательные технологии, такие как средства чтения с экрана, будет проще использовать эти средства пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="43995-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> 

<span data-ttu-id="43995-307">Эти усовершенствования меняют предыдущее поведение, например порядок фокуса клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="43995-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>
### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="43995-308">Конструктор рабочих процессов Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="43995-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="43995-309">Ниже перечислены изменения специальных возможностей в конструкторе рабочих процессов:</span><span class="sxs-lookup"><span data-stu-id="43995-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="43995-310">Для некоторых элементов управления изменена последовательность табуляции при переходе слева направо и сверху вниз:</span><span class="sxs-lookup"><span data-stu-id="43995-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="43995-311">Окно инициализации корреляции для установки данных корреляции для действия <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="43995-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="43995-312">Окно определения содержания для действий <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="43995-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="43995-313">Большее число функций доступно с клавиатуры:</span><span class="sxs-lookup"><span data-stu-id="43995-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="43995-314">При редактировании свойств действия группы свойств можно сворачивать с помощью клавиатуры в том случае, если они впервые получают фокус.</span><span class="sxs-lookup"><span data-stu-id="43995-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="43995-315">Значки предупреждений теперь доступны с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="43995-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="43995-316">Кнопка **Дополнительные свойства** в окне **Свойства** теперь доступна с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="43995-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="43995-317">Пользователи могут с помощью клавиатуры получать доступ к элементам заголовка в областях **Аргументы** и **Переменные** в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="43995-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="43995-318">Улучшена видимость находящихся в фокусе элементов, например в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="43995-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="43995-319">Добавление строк в сетки данных, используемые конструктором рабочих процессов и конструкторами действий.</span><span class="sxs-lookup"><span data-stu-id="43995-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="43995-320">Переход по клавише TAB между полями в действиях <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="43995-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="43995-321">Установка значений по умолчанию для переменных или аргументов</span><span class="sxs-lookup"><span data-stu-id="43995-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="43995-322">Средства чтения с экрана теперь правильно распознают следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="43995-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="43995-323">Точки останова, установленные в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="43995-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="43995-324">Действия <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> и <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="43995-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="43995-325">Содержимое действия <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="43995-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="43995-326">Целевой тип действия <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="43995-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="43995-327">Поле со списком "Исключение" и раздел Finally действия <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="43995-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="43995-328">Поле со списком "Тип сообщений", разделитель в окне "Добавить инициализаторы корреляции", окно "Определение содержимого", а также окно "Определение корреляции" в действиях сообщений (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="43995-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="43995-329">Переходы и назначения переходов конечного автомата.</span><span class="sxs-lookup"><span data-stu-id="43995-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="43995-330">Заметки и соединители для действий <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="43995-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="43995-331">Контекстные меню действий, вызываемые при щелчке правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="43995-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="43995-332">Редакторы значений свойств, кнопка "Очистить условия поиска", кнопки сортировки "По категории" и "По алфавиту", а также диалоговое окно "Редактор выражений" в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="43995-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="43995-333">Величина масштаба в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="43995-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="43995-334">Разделитель в действиях <xref:System.Activities.Statements.Parallel> и <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="43995-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="43995-335">Действие <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="43995-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="43995-336">Окно "Выбор типов" для действий словаря (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="43995-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="43995-337">Окно поиска и выбора типа .NET.</span><span class="sxs-lookup"><span data-stu-id="43995-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="43995-338">Элемент иерархической навигации в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="43995-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="43995-339">Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости многих частей конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.</span><span class="sxs-lookup"><span data-stu-id="43995-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="43995-340">См. также</span><span class="sxs-lookup"><span data-stu-id="43995-340">See also</span></span>

- [<span data-ttu-id="43995-341">Новые возможности .NET Framework</span><span class="sxs-lookup"><span data-stu-id="43995-341">What's new in the .NET Framework</span></span>](whats-new.md)

