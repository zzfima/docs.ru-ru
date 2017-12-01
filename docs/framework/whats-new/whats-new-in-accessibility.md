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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Новые возможности специальных возможностей в .NET Framework

Платформа .NET Framework намеревается делать приложения более доступность для пользователей. Специальные возможности позволяют приложению обеспечить соответствующие возможности при работе с поддержкой специальных возможностей. Начиная с платформы .NET Framework 4.7.1, платформа .NET Framework включает большое количество более удобным, позволяющие разработчикам создавать приложения со специальными возможностями. 

Новые функции специальных возможностей будут включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии. Кроме того, приложения, которые более раннюю версию платформы .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии можно выбрать поведений устаревших специальных возможностей (и тем самым согласие на использование более удобным в платформе .NET Framework 4.7.1), добавив следующий параметр для [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Аналогичным образом, приложения, предназначенные для версий платформы .NET Framework, начиная с 4.7.1 можно отключить, добавив следующий параметр, чтобы специальные возможности [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) элемент в [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) раздел файла конфигурации приложения. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Новые возможности специальных возможностей в .NET Framework 4.7.1

Платформа .NET Framework 4.7.1 включает новые функции специальных возможностей в следующих областях:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Усовершенствования чтения экрана**

Если включены более удобным, платформа .NET Framework 4.7.1 включает следующие улучшения, которые влияют на средства чтения с экрана:

- В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.Expander> элементы управления были объявлены с экрана, как кнопки. Начиная с платформы .NET Framework 4.7.1, они правильно воспринимаются как расширяемые и свертываемые группы.

- В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.DataGridCell> элементы управления были объявлены с экрана, как «custom». Начиная с платформы .NET Framework 4.7.1, они теперь правильно воспринимаются как (локализованный) ячейки сетки данных.
 
- Начиная с .NET Framework 4.7.1 чтения с экрана сообщать имя редактируемого <xref:System.Windows.Controls.ComboBox>.

- В .NET Framework 4.7 и более ранних версиях <xref:System.Windows.Controls.PasswordBox> элементы управления были объявлены как «нет элемент в представлении» или бы в противном случае неправильное поведение. Эта проблема исправлена, начиная с .NET Framework 4.7.1.     

**Поддержка UIAutomation LiveRegion**

Например, Экранный диктор для пользователей чтения с экрана содержимое пользовательского интерфейса приложения, обычно озвучивания текста вывод содержимого пользовательского интерфейса, который находится в фокусе. Тем не менее если элемент пользовательского интерфейса изменяется и не имеет фокуса, пользователь не может получать уведомления и пропустить важные сведения. Динамическая областей стремятся решить эту проблему. Разработчик может использовать их для информирования чтения с экрана или любым другим клиентом UIAutomation, важные изменения в элемент пользовательского интерфейса. Как и когда средства чтения с экрана можно настроить для оповещения пользователя этого изменения. 

Для поддержки динамической областей, для WPF были добавлены следующие API:

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> И <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> поля, которые идентифицируют **LiveSetting** свойство и **LiveRegionChanged** событий. Они могут быть заданы с помощью XAML.

- **AutomationProperties.LiveSetting** вложенное свойство зависимостей, который уведомляет чтения с экрана важные изменения пользовательского интерфейса для пользователя.

- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> Свойство, которое идентифицирует **AutomationProperties.LiveSetting** вложенное свойство.
 
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> Метод, который может быть переопределен **LiveSetting** значение.

- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> И <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> методы get и set **LiveSetting** значение.
 
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> Перечисления, который определяет следующие возможные **LiveSetting** значения:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. Элемент не отправлять уведомления при изменении содержимого динамической области.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. Элемент отправляет уведомления, не прерывающие работу, при изменении содержимого динамической области.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. Элемент отправляет уведомления, прерывающие работу, при изменении содержимого динамической области.   

Можно создать, задав LiveRegion **AutomationProperties.LiveSetting** свойство элемента, как показано в следующем примере:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

При изменении данных в области динамической и необходимо проинформировать чтения с экрана, можно явно вызвать событие, как показано в следующем примере.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Высокая контрастность**

Начиная с платформы .NET Framework 4.7.1, в высокой контрастности внесены изменения для различных элементов управления WPF. Они будут отображаться при <xref:System.Windows.SystemParameters.HighContrast%2A> задана тема. К ним относятся следующие методы.

- Элемент управления <xref:System.Windows.Controls.Expander>

    Фокус visual для <xref:System.Windows.Controls.Expander> теперь отображается элемент управления. Визуальные элементы клавиатуры для <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, и <xref:System.Windows.Controls.RadioButton> элементы управления также являются видимыми. Пример:

    До: 
    
    ![Элемент управления Expander с фокусом, прежде чем более удобным](media/expander-before.png)

    После: 

    ![Элемент управления Expander с фокусом после более удобным](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>и <xref:System.Windows.Controls.RadioButton> элементов управления
 
    Текст в <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> элементы управления теперь стало проще см. При выборе режима высокой контрастности темы. Пример:

    До: 

    ![Высокая контрастность "переключатель" с фокусом, прежде чем более удобным](media/radio-button-before.png)
    
    После: 

    ![Высокая контрастность "переключатель" с фокусом после более удобным](media/radio-button-after.png)

- Элемент управления <xref:System.Windows.Controls.ComboBox>
 
    Начиная с .NET Framework 4.7.1, границы отключенного <xref:System.Windows.Controls.ComboBox> элемент управления является цвет отключенного текста. Пример:
    
    До: 

     ![Поле со списком отключено границей и текстом перед более удобным](media/combo-disabled-before.png)

    После:   

     ![После более удобным ComboBox отключен границей и текстом](media/combo-disabled-after.png)

    Кроме того отключен и имеющего фокус кнопки использовать цвет правильный темы.

    До:

    ![Кнопка цвета темы до более удобным](media/button-themes-before.png) 
    
    После: 

    ![Кнопка цвета темы после более удобным](media/button-themes-after.png) 

    Наконец, в .NET Framework 4.7 и более ранних версий, установка <xref:System.Windows.Controls.ComboBox> стиль элемента управления для `Toolbar.ComboBoxStyleKey` вызвала стрелку раскрывающегося списка, чтобы быть скрытым. Эта проблема исправлена, начиная с .NET Framework 4.7.1. Пример:

    До: 

    ![Toolbar.ComboBoxStyleKey до более удобным](media/comboboxstylekey-before.png) 
    
    После: 

    ![Toolbar.ComboBoxStyleKey после более удобным](media/comboboxstylekey-after.png) 

- Элемент управления <xref:System.Windows.Controls.DataGrid>

    Начиная с .NET Framework 4.7.1, стрелку индикатор сортировки в <xref:System.Windows.Controls.DataGrid> управляет теперь использует исправить цвета темы. Пример:

    До: 

    ![Индикатор стрелку сортировки до более удобным](media/sort-indicator-before.png) 
    
    После:   
 
    ![Индикатор стрелку сортировки после более удобным](media/sort-indicator-after.png) 
    
    Кроме того в .NET Framework 4.7 и более ранних версий, стиль ссылки по умолчанию изменен на неверный цвет, мыши в режиме высокой контрастности. Это разрешается, начиная с .NET Framework 4.7.1. Аналогичным образом <xref:System.Windows.Controls.DataGrid> столбцы флажок использует ожидаемый цвета для отзывов фокус клавиатуры, начиная с .NET Framework 4.7.1.

    До: 

    ![Стиль ссылки по умолчанию DataGrid до более удобным](media/default-link-style-before.png) 
 
    После:    
  
    ![Стиль ссылки по умолчанию DataGrid после более удобным](media/default-link-style-after.png)  

Дополнительные сведения об улучшениях специальных возможностей WPF в платформе .NET Framework 4.7.1 см. в разделе [более удобным в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

## <a name="windows-forms-accessibility-improvements"></a>Улучшения специальных возможностей Windows Forms

В платформе .NET Framework 4.7.1 Windows Forms (WinForms) содержит специальные возможности изменения в следующих областях.

**Улучшенное отображение в режиме высокой контрастности**

Начиная с .NET Framework 4.7.1 различные элементы управления WinForms обеспечивают улучшенную подготовки к просмотру в режимы Высокая контрастность, доступные в операционной системе. Windows 10 были изменены для некоторых системных цветов, высокая контрастность и Windows Forms основана на платформе Windows 10 Win32. Для получения наилучших результатов выполните самую последнюю версию Windows и выбрать последние изменения операционной системы, добавление в файл app.manifest в тестовое приложение и отменить преобразование в комментарий Windows 10 поддерживается ОС строки таким образом, следующее:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Некоторые примеры изменения режима высокой контрастности.

- Пометок в <xref:System.Windows.Forms.MenuStrip> элементов более удобны для просмотра.

- При выборе отключены <xref:System.Windows.Forms.MenuStrip> элементов более удобны для просмотра.

- Текст в выбранной <xref:System.Windows.Forms.Button> управления отличается от выбора цвета.

- Отключенного текста является более удобным для чтения. Пример:

    До:

    ![Отключенного текста до более удобным](media/wf-disabled-before.png) 

    После:

    ![Отключенного текста после более удобным](media/wf-disabled-after.png) 

- Усовершенствования режима высокой контрастности в диалоговое окно исключения потока.

**Улучшенная поддержка Экранный диктор**

Windows Forms в .NET Framework 4.7.1 включает следующие улучшения специальных возможностей для Экранный диктор.

- <xref:System.Windows.Forms.MonthCalendar> Элемент управления может быть доступен Экранный диктор, а также с другими средствами автоматизации пользовательского интерфейса.

- <xref:System.Windows.Forms.CheckedListBox> Управления оповещает Экранный диктор состояния флажка элемента изменился, и пользователь получает уведомление, что они изменили значение элемента списка.
 
- <xref:System.Windows.Forms.DataGridViewCell> Экранный диктор управления сообщает правильное состояние только для чтения.
 
- Экранный диктор сможете прочитать отключено <xref:System.Windows.Forms.ToolStripMenuItem> текста, в то время как ранее он пропустить пунктов меню отключен.

**Улучшенная поддержка шаблонов UIAutomation специальных возможностей**

Начиная с платформы .NET Framework 4.7.1, разработчики средств специальных возможностей технологии могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms. Эти улучшения специальных возможностей:

- <xref:System.Windows.Forms.ComboBox> И <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон expand collapse](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> Теперь поддерживает [шаблон toggle](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- <xref:System.Windows.Forms.ToolStripItem> Управления поддерживает <xref:System.Windows.Automation.AutomationElement.Name> свойство и [шаблон expand collapse](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.NumericUpDown> И <xref:System.Windows.Forms.DomainUpDown> элементы управления поддерживают <xref:System.Windows.Automation.automationElement.Name> свойство.

**Свойство улучшенное взаимодействие с браузером**

Начиная с платформы .NET Framework 4.7.1, Windows Forms включает в себя:

- Улучшения с помощью клавиатуры через различные окна выбора раскрывающегося списка.
- Сокращение ненужных позицию табуляции.
- Улучшенные отчеты типов элементов управления.
- Экранный диктор улучшенное поведение.
 
## <a name="see-also"></a>См. также
[Новые возможности .NET Framework](whats-new.md)   
 