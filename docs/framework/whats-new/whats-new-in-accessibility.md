---
title: "Улучшения специальных возможностей в .NET Framework"
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
ms.workload: dotnet
ms.openlocfilehash: 9fe4b24f14dd8f08d1168cc26b91e04faa4bf183
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Улучшения специальных возможностей в .NET Framework

Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей. Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей. Начиная с .NET Framework 4.7.1, платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения. 

Новые специальные возможности включены по умолчанию для приложений, ориентированных на .NET Framework 4.7.1 или более поздней версии. Кроме того, приложения, которые ориентированы на более раннюю версию .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей в .NET Framework 4.7.1), добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Аналогичным образом, приложения, ориентированные на версии .NET Framework, начиная с 4.7.1, могут отключить специальные возможности, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) файла конфигурации приложения. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Улучшения специальных возможностей в .NET Framework 4.7.1

.NET Framework 4.7.1 включает новые специальные возможности в следующих областях:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

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

## <a name="windows-forms-accessibility-improvements"></a>Улучшения специальных возможностей в Windows Forms

В компонент Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:

**Улучшенное отображение в режиме высокой контрастности**

Начиная с .NET Framework 4.7.1, различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе. В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10. Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:

```xml
<!– Windows 10 –>
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
 
- Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.automationElement.Name>.

**Улучшенное взаимодействие с обозревателем свойств**

Начиная с .NET Framework 4.7.1, компонент Windows Forms включает в себя следующее:

- Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.
- Сокращение ненужных позиций табуляции.
- Улучшенные отчеты о типах элементов управления.
- Улучшенная работа экранного диктора.
 
## <a name="see-also"></a>См. также
[Новые возможности .NET Framework](whats-new.md)   
 