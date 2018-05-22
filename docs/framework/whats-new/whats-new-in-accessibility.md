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
ms.openlocfilehash: 7fe7e15e482028b9988d7e560b98be19b6c07427
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Улучшения специальных возможностей в .NET Framework

Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей. Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей. Начиная с .NET Framework 4.7.1, платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения. 

## <a name="accessibility-switches"></a>Переключатель специальных возможностей

Вы можете включить в приложении функции специальных возможностей, если оно предназначено для .NET Framework 4.7 или более ранней версии, но выполняется на платформе .NET Framework 4.7.1 или более поздней версии. Вы также можете настроить в приложении использование компонентов прежних версий (и не использовать преимущества функций специальных возможностей), если оно предназначен для .NET Framework 4.7.1 или более поздней версии. У каждой версии платформы .NET Framework с функциями специальных возможностей есть специальный переключатель, который можно добавить в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения. Ниже приведены поддерживаемые переключатели:

|Версия|Параметр|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Использование преимуществ усовершенствованных специальных возможностей

Новые специальные возможности включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии. Кроме того, приложения, которые ориентированы на более раннюю версию .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей). Для этого добавьте следующие переключатели в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установите для них значение `false`. В следующем примере показано, как принять усовершенствованные специальные возможности, представленные в .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Если вы решили включить функции специальных возможностей из более поздней версии .NET Framework, необходимо явным образом включить эти функции из более ранних версий платформы .NET Framework. Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1 и 4.7.2 требуется следующий элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Восстановление поведения из предыдущих версий

Для приложений, ориентированных на версии .NET Framework, начиная с 4.7.1, можно отключить функции специальных возможностей, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установив значение `true`. Например, следующая конфигурация задает отказ от функций специальных возможностей, представленных в .NET Framework 4.7.2:  

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a>Улучшения специальных возможностей в .NET Framework 4.7.2

.NET Framework 4.7.2 включает новые функции специальных возможностей в следующих областях:

- [Windows Forms](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>
### <a name="windows-forms"></a>Windows Forms

**Определенные в ОС цвета в темах высокой контрастности**

Начиная с .NET Framework 4.7.2 Windows Forms использует цвета, определенные в операционной системе, в темах высокой контрастности. Это влияет на следующие элементы:

- Стрелка раскрывающегося списка элемента управления <xref:System.Windows.Forms.ToolStripDropDownButton>.

- Элементы управления <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox>, у которых для параметра <xref:System.Windows.Forms.ButtonBase.FlatStyle> установлено значение <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> или <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>. Ранее выбранные цвета текста и фона не были контрастными и текст было сложно читать.

- Элементы управления, содержащиеся в <xref:System.Windows.Forms.GroupBox>, у которого для свойства <xref:System.Windows.Forms.Control.Enabled> установлено значение `false`.
 
- Элементы управления <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> и <xref:System.Windows.Forms.ToolStripDropDownButton>, которые имеют повышенное значение контрастности яркости в режиме высокой контрастности.

- Свойство <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> класса <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Усовершенствования экранного диктора**

Начиная с .NET Framework 4.7.2 усовершенствована поддержка экранного диктора:

- Он сообщает значение свойства <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> при объявлении текста <xref:System.Windows.Forms.ToolStripMenuItem>. 

- Он указывает, когда для свойства <xref:System.Windows.Forms.Control.Enabled> элемента <xref:System.Windows.Forms.ToolStripMenuItem> задано значение `false`.

- Он предоставляет отзыв о состоянии флажка, если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> задано значение `true`.

- Порядок фокуса экранного диктора в режиме сканирования согласуется с визуальным порядком элементов управления в диалоговом окне загрузки ClickOnce.

**Усовершенствования DataGridView**

Начиная с .NET Framework 4.7.2 элемент управления <xref:System.Windows.Forms.DataGridView> вносит следующие улучшения специальных возможностей:

- Строки можно сортировать с помощью клавиатуры. Пользователь может нажать клавишу F3, чтобы выполнить сортировку по текущему столбцу.

- Когда <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, заголовок столбца меняет цвет для указания на текущий столбец, когда пользователь переходит по ячейкам в текущей строке.

- Свойство <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> возвращает правильный родительский элемент управления.

**Улучшенные визуальные подсказки**

- Элементы управления <xref:System.Windows.Forms.RadioButton> и <xref:System.Windows.Forms.CheckBox> с пустым свойством <xref:System.Windows.Forms.ButtonBase.Text> отображают индикатор фокуса при получении фокуса.

**Улучшенная поддержка сетки свойств**

- Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> теперь возвращают `true` для <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> свойства только в том случае, если включен элемент PropertyGrid.

- Дочерние элементы элемента управления <xref:System.Windows.Forms.PropertyGrid> возвращают `false` для свойства <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> только в том случае, если элемент PropertyGrid может быть изменен пользователем.

**Улучшение навигации с помощью клавиатуры**

- Элемент управления <xref:System.Windows.Forms.ToolStripButton> позволяет отображать фокус, если он содержится в <xref:System.Windows.Forms.ToolStripPanel>, для свойства <xref:System.Windows.Forms.ToolStripPanel.TabStop> которого задано значение `true`

<a name="wpf472"></a>
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Изменения элементов управления CheckBox и RadioButton**

В .NET Framework 4.7.1 и более ранних версий элементы управления <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> и <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> WPF имеют несогласованные и (в классической теме и теме высокой контрастности) неправильные визуальные элементы фокуса.  Это происходит в случаях, когда для элементов управления не задано какое-либо содержимое.  Это может затруднять переход между темами и отображение визуального элемента фокуса.

В .NET Framework 4.7.2 эти визуальные элементы стали более согласованными в разных темах и более видимыми в классической и контрастной темах.

**Элементы управления WinForms, размещенные в приложении WPF**

При использовании элемента управления WinForms, размещенного в приложении WPF в .NET Framework 4.7.1 и более ранних версий, пользователи не могли выйти из слоя WinForms с помощью клавиши табуляции, если первый или последний элемент управления в слое был элементом управления <xref:System.Windows.Forms.Integration.ElementHost> WPF. В .NET Framework 4.7.2 пользователи теперь могут выйти из слоя WinForms с помощью клавиши табуляции.

Однако автоматизированные приложения, которые зависят от постоянного нахождения фокуса в слое WinForms, могут работать некорректно.

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Улучшения специальных возможностей в .NET Framework 4.7.1

.NET Framework 4.7.1 включает новые специальные возможности в следующих областях:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [Веб-элементы управления ASP.NET](#aspnet471)

- [.NET SDK Tools](#tools471)

- [Конструктор рабочих процессов Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Улучшения средств чтения с экрана**

Если включены улучшения специальных возможностей, .NET Framework 4.7.1 содержит следующие усовершенствования, касающиеся средств чтения с экрана:

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.Expander> объявлялись средствами чтения с экрана как кнопки. Начиная с .NET Framework 4.7.1, они правильно объявляются как развертываемые/свертываемые группы.

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.DataGridCell> объявлялись средствами чтения с экрана как настраиваемые. Начиная с .NET Framework 4.7.1, они правильно объявляются как ячейка сетки данных (локализованная).
 
- Начиная с .NET Framework 4.7.1, средства чтения с экрана объявляют имя изменяемого <xref:System.Windows.Controls.ComboBox>.

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.PasswordBox> объявлялись как "в представлении нет элементов" или имели иное неправильное поведение. Начиная с .NET Framework 4.7.1, эта проблема устранена.

**Поддержка динамических областей автоматизации пользовательского интерфейса**

Средства чтения с экрана, такие как экранный диктор, помогают людям читать содержимое пользовательского интерфейса приложения. Обычно для этого используется преобразование текста в речь для содержимого, находящегося в фокусе. Однако если элемент пользовательского интерфейса изменяется и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения. Динамические области призваны решить эту проблему. Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента автоматизации пользовательского интерфейса о важных изменениях элемента пользовательского интерфейса. После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении. 

Для поддержки динамических областей в WPF добавлены следующие API:

- Поля <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, которые идентифицируют свойство **LiveSetting** и событие **LiveRegionChanged**. Их можно задать с помощью XAML.

- Присоединенное свойство **AutomationProperties.LiveSetting**, средство чтения с экрана, уведомляющее о том, насколько важно изменение пользовательского интерфейса для пользователя.

- Свойство<xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, которое идентифицирует присоединенное свойство **AutomationProperties.LiveSetting**.
 
- Метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, который можно переопределить для предоставления значения **LiveSetting**.

- Методы <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, которые возвращают и задают значение **LiveSetting**.
 
- Перечисление <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, которое определяет следующие возможные значения **LiveSetting**:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. Элемент не отправляет уведомления при изменении содержимого динамической области.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.   

Вы можете создать динамическую область, задав свойство **AutomationProperties.LiveSetting** для нужного элемента, как показано в следующем примере:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Когда данные в динамической области изменяются и вам нужно проинформировать средство чтения с экрана, можно явно вызвать событие, как показано в следующем примере.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Высокая контрастность**

Начиная с .NET Framework 4.7.1, внесены улучшения в функции высокой контрастности для различных элементов управления WPF. Теперь они видны, когда задана тема <xref:System.Windows.SystemParameters.HighContrast%2A>. Сюда входит следующее.

- Элемент управления <xref:System.Windows.Controls.Expander>

    Визуальный элемент фокуса для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается. Визуальные элементы клавиатуры для элементов управления <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.RadioButton> также видимы. Пример:

    До: 
    
    ![Элемент управления Expander с фокусом до внесения улучшений](media/expander-before.png)

    После: 

    ![Элемент управления Expander с фокусом после внесения улучшений](media/expander-after.png)

- Элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton>
 
    Текст в элементах управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> теперь стало проще читать, когда он выбран при использовании тем с высокой контрастностью. Пример:

    До: 

    ![Переключатель высокой контрастности до внесения улучшений](media/radio-button-before.png)
    
    После: 

    ![Переключатель высокой контрастности после внесения улучшений](media/radio-button-after.png)

- Элемент управления <xref:System.Windows.Controls.ComboBox>
 
    Начиная с .NET Framework 4.7.1, граница отключенного элемента управления <xref:System.Windows.Controls.ComboBox> имеет цвет отключенного текста. Пример:
    
    До: 

     ![Отключенная граница и текст поля со списком до внесения улучшений](media/combo-disabled-before.png)

    После:   

     ![Отключенная граница и текст поля со списком после внесения улучшений](media/combo-disabled-after.png)

    Кроме того, отключенные и находящиеся в фокусе кнопки используют правильный цвет темы.

    До:

    ![Цвета темы для кнопок до внесения улучшений](media/button-themes-before.png) 
    
    После: 

    ![Цвета темы для кнопок после внесения улучшений](media/button-themes-after.png) 

    Наконец, в .NET Framework 4.7 и более ранних версий установка стиля элемента управления <xref:System.Windows.Controls.ComboBox> в значение `Toolbar.ComboBoxStyleKey` приводила к тому, что стрелка раскрывающегося списка была невидимой. Начиная с .NET Framework 4.7.1, эта проблема устранена. Пример:

    До: 

    ![Toolbar.ComboBoxStyleKey до внесения улучшений](media/comboboxstylekey-before.png) 
    
    После: 

    ![Toolbar.ComboBoxStyleKey после внесения улучшений](media/comboboxstylekey-after.png) 

- Элемент управления <xref:System.Windows.Controls.DataGrid>

    Начиная с .NET Framework 4.7.1, стрелка индикатора сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> теперь использует правильные цвета темы. Пример:

    До: 

    ![Стрелка индикатора сортировки до внесения улучшений](media/sort-indicator-before.png) 
    
    После:   
 
    ![Стрелка индикатора сортировки после внесения улучшений](media/sort-indicator-after.png) 
    
    Кроме того, в .NET Framework 4.7 и более ранних версий стиль ссылки по умолчанию изменялся на неправильный цвет при наведении указателя мыши в режимах высокой контрастности. Начиная с .NET Framework 4.7.1, эта проблема устранена. Аналогичным образом, столбец флажка <xref:System.Windows.Controls.DataGrid> использует ожидаемые цвета для отзывов на фокус клавиатуры, начиная с .NET Framework 4.7.1.

    До: 

    ![Стиль ссылки по умолчанию DataGrid до внесения улучшений](media/default-link-style-before.png) 
 
    После:    
  
    ![Стиль ссылки по умолчанию DataGrid после внесения улучшений](media/default-link-style-after.png)  

Дополнительные сведения об улучшениях специальных возможностей WPF в .NET Framework 4.7.1 см. в разделе [Улучшения специальных возможностей в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>
## <a name="windows-forms-accessibility-improvements"></a>Улучшения специальных возможностей в Windows Forms

В компонент Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:

**Улучшенное отображение в режиме высокой контрастности**

Начиная с .NET Framework 4.7.1, различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе. В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10. Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Некоторые примеры изменения режима высокой контрастности:

- Лучше читаются флажки в элементах <xref:System.Windows.Forms.MenuStrip>.

- Лучше читаются выбранные отключенные элементы <xref:System.Windows.Forms.MenuStrip>.

- Текст в выбранном <xref:System.Windows.Forms.Button> элементе управления отличается от цвета выбора.

- Отключенный текст проще читать. Пример:

    До:

    ![Отключенный текст до внесения улучшений](media/wf-disabled-before.png) 

    После:

    ![Отключенный текст после внесения улучшений](media/wf-disabled-after.png) 

- Усовершенствования режима высокой контрастности в диалоговом окне исключения потока.

**Улучшенная поддержка экранного диктора**

Компонент Windows Forms в .NET Framework 4.7.1 содержит следующие улучшения специальных возможностей для экранного диктора:

- К элементу управления <xref:System.Windows.Forms.MonthCalendar> может обратиться как экранный диктор, так и любое другое средство автоматизации пользовательского интерфейса.

- Элемент управления <xref:System.Windows.Forms.CheckedListBox> оповещает экранный диктор об изменении состояния флажка элемента, чтобы пользователь узнал, что значение элемента списка изменилось.
 
- Элемент управления <xref:System.Windows.Forms.DataGridViewCell> сообщает правильное состояние доступа только для чтения экранному диктору.
 
- Теперь экранный диктор может прочитать отключенный текст <xref:System.Windows.Forms.ToolStripMenuItem>, хотя раньше он пропускал отключенные пункты меню.

**Улучшенная поддержка шаблонов специальных возможностей автоматизации пользовательского интерфейса**

Начиная с .NET Framework 4.7.1, разработчики средств специальных возможностей могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms. Некоторые из этих улучшений специальных возможностей:

- <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> теперь поддерживает [шаблон переключения](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.

**Улучшенное взаимодействие с обозревателем свойств**

Начиная с .NET Framework 4.7.1, компонент Windows Forms включает в себя следующее:

- Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.
- Сокращение ненужных позиций табуляции.
- Улучшенные отчеты о типах элементов управления.
- Улучшенная работа экранного диктора.
 
<a name="aspnet471"></a>
## <a name="aspnet-web-controls"></a>Веб-элементы управления ASP.NET

Начиная с .NET Framework 4.7.1 и Visual Studio 2017 15.3 в ASP.NET улучшена работа веб-элементов управления ASP.NET с технологией специальных возможностей в Visual Studio. Внесены следующие изменения:

- Изменения для реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления, например в диалоговом окне **Добавить поле** в мастере **представления сведений** или в диалоговом окне **Настройка ListView** в мастере **ListView**.

- Изменения для улучшенного отображения в режиме высокой контрастности, например в **редакторе полей страничного навигатора данных**.

- Изменения для улучшения навигации с помощью клавиатуры для таких элементов, как диалоговое окно **Поля** в мастере **полей страничного навигатора**, диалоговое окно **Настроить ObjectContext** или **Настроить выбор данных** в мастере **настройки источника данных**.

<a name="tools471"></a>
## <a name="net-sdk-tools"></a>.NET SDK Tools

В [редакторе конфигурации (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) и [средстве Service Trace Viewer (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) были устранены различные ошибки специальных возможностей. В основном это были незначительные проблемы, например не определялось имя или некорректно реализовывались шаблоны автоматизации пользовательского интерфейса. Многие пользователи могли не замечать неверные значения, но пользователям, использующим вспомогательные технологии, такие как средства чтения с экрана, будет проще использовать эти средства пакета SDK. 

Эти усовершенствования меняют предыдущее поведение, например порядок фокуса клавиатуры.

<a name="wf471"></a>
## <a name="windows-workflow-foundation-wf-workflow-designer"></a>Конструктор рабочих процессов Windows Workflow Foundation (WF)

Ниже перечислены изменения специальных возможностей в конструкторе рабочих процессов:

- Для некоторых элементов управления изменена последовательность табуляции при переходе слева направо и сверху вниз:

  - Окно инициализации корреляции для установки данных корреляции для действия <xref:System.ServiceModel.Activities.InitializeCorrelation>.

  - Окно определения содержания для действий <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>.

- Большее число функций доступно с клавиатуры:

  - При редактировании свойств действия группы свойств можно сворачивать с помощью клавиатуры в том случае, если они впервые получают фокус.

  - Значки предупреждений теперь доступны с клавиатуры.

  - Кнопка **Дополнительные свойства** в окне **Свойства** теперь доступна с клавиатуры.

  - Пользователи могут с помощью клавиатуры получать доступ к элементам заголовка в областях **Аргументы** и **Переменные** в конструкторе рабочих процессов.

- Улучшена видимость находящихся в фокусе элементов, например в следующих случаях:

  - Добавление строк в сетки данных, используемые конструктором рабочих процессов и конструкторами действий.

  - Переход по клавише TAB между полями в действиях <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>.

  - Установка значений по умолчанию для переменных или аргументов

- Средства чтения с экрана теперь правильно распознают следующие объекты:

  - Точки останова, установленные в конструкторе рабочих процессов.

  - Действия <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> и <xref:System.ServiceModel.Activities.CorrelationScope>.
  - Содержимое действия <xref:System.ServiceModel.Activities.Receive>.

  - Целевой тип действия <xref:System.Activities.Statements.InvokeMethod>.

  - Поле со списком "Исключение" и раздел Finally действия <xref:System.Activities.Statements.TryCatch>.

  - Поле со списком "Тип сообщений", разделитель в окне "Добавить инициализаторы корреляции", окно "Определение содержимого", а также окно "Определение корреляции" в действиях сообщений (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>).

  - Переходы и назначения переходов конечного автомата.

  - Заметки и соединители для действий <xref:System.Activities.Statements.FlowDecision>.

  - Контекстные меню действий, вызываемые при щелчке правой кнопкой мыши.

  - Редакторы значений свойств, кнопка "Очистить условия поиска", кнопки сортировки "По категории" и "По алфавиту", а также диалоговое окно "Редактор выражений" в сетке свойств.

  - Величина масштаба в конструкторе рабочих процессов.

  - Разделитель в действиях <xref:System.Activities.Statements.Parallel> и <xref:System.Activities.Statements.Pick>.

  - Действие <xref:System.Activities.Statements.InvokeDelegate>.

  - Окно "Выбор типов" для действий словаря (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` и т. д.).

  - Окно поиска и выбора типа .NET.

  - Элемент иерархической навигации в конструкторе рабочих процессов.

- Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости многих частей конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.

## <a name="see-also"></a>См. также

[Новые возможности .NET Framework](whats-new.md)
 
