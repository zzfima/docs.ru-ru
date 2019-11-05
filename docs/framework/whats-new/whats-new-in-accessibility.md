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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Улучшения специальных возможностей в .NET Framework

Платформа .NET Framework ориентирована на то, чтобы сделать приложения более доступными для ваших пользователей. Специальные возможности позволяют приложению предоставлять соответствующую функциональность пользователям технологий с поддержкой специальных возможностей. Начиная с .NET Framework 4.7.1 платформа .NET Framework включает большое число улучшений специальных возможностей, позволяющих разработчикам создавать доступные приложения.

## <a name="accessibility-switches"></a>Переключатель специальных возможностей

Вы можете включить в приложении функции специальных возможностей, если оно предназначено для .NET Framework 4.7 или более ранней версии, но выполняется на платформе .NET Framework 4.7.1 или более поздней версии. Вы также можете настроить в приложении использование компонентов прежних версий (и не использовать преимущества функций специальных возможностей), если оно предназначено для .NET Framework 4.7.1 или более поздней версии. У каждой версии платформы .NET Framework с функциями специальных возможностей есть специальный переключатель, который можно добавить в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения. Ниже приведены поддерживаемые переключатели:

|Version|Параметр|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|
|.NET Framework 4.8|"Switch.UseLegacyAccessibilityFeatures.3"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Использование преимуществ усовершенствованных специальных возможностей

Новые специальные возможности включены по умолчанию для приложений, предназначенных для .NET Framework 4.7.1 или более поздней версии. Кроме того, приложения, которые предназначены для более ранней версии .NET Framework, но работают на платформе .NET Framework 4.7.1 или более поздней версии, могут явно отказаться от устаревших вариантов специальных возможностей (и тем самым согласиться на использование улучшений специальных возможностей). Для этого добавьте параметры в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установите для них значение `false`. В следующем примере показано, как принять усовершенствованные специальные возможности, представленные в .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Если вы решили включить функции специальных возможностей из более поздней версии .NET Framework, необходимо явным образом включить эти функции из более ранних версий платформы .NET Framework. Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1 и 4.7.2 требуется следующий элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

Для использования в приложении усовершенствованных специальных возможностей из .NET Framework 4.7.1, 4.7.2 и 4.8 требуется следующий элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Восстановление поведения из предыдущих версий

Для приложений, ориентированных на версии .NET Framework, начиная с 4.7.1, можно отключить функции специальных возможностей, добавив следующий параметр в элемент [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [`<runtime>`](../configure-apps/file-schema/runtime/index.md) файла конфигурации приложения и установив значение `true`. Например, следующая конфигурация задает отказ от функций специальных возможностей, представленных в .NET Framework 4.7.2:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a>Улучшения специальных возможностей в .NET Framework 4.8

Платформа .NET Framework 4.8 включает новые функции специальных возможностей в следующих областях:

- [Windows Forms](#winforms48)

- [Windows Presentation Foundation (WPF)](#wpf48)

- [Конструктор рабочих процессов Windows Workflow Foundation (WF)](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a>Windows Forms

В .NET Framework 4.8 ко многим часто используемым элементам управления Windows Forms добавлена поддержка динамических областей и событий уведомлений. Кроме того, добавлена поддержка подсказок при переходе к элементам управления с помощью клавиатуры.

**Поддержка динамических областей для элементов управления типа Label и StatusStrip в модели автоматизации пользовательского интерфейса Microsoft Windows**

Динамические области в модели автоматизации пользовательского интерфейса Microsoft Windows позволяют разработчикам приложений уведомлять средства чтения с экрана об изменении текста в элементах управления, который находятся не там, где пользователь работает в настоящее время. Например, это полезно в случае с элементом управления <xref:System.Windows.Forms.StatusStrip>, в котором отображается состояние подключения. Разработчику может быть необходимо уведомить средство чтения с экрана об изменении состояния, например утере подключения.

Начиная с .NET Framework 4.8 динамические области в модели автоматизации пользовательского интерфейса Microsoft Windows реализованы для элементов управления Windows Forms <xref:System.Windows.Forms.Label> и <xref:System.Windows.Forms.StatusStrip>. Например, в следующем коде динамическая область используется в элементе управления <xref:System.Windows.Forms.Label> с именем `label1`:

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

Экранный диктор произносит "Готово" независимо от того, с каким элементом в приложении взаимодействует пользователь.

Вы также можете реализовать <xref:System.Windows.Forms.UserControl> как динамическую область:

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

**События уведомлений в модели автоматизации пользовательского интерфейса Microsoft Windows**

Событие уведомления модели автоматизации пользовательского интерфейса Microsoft Windows, появившееся в Windows 10 Fall Creators Update, позволяет приложению создавать событие модели автоматизации пользовательского интерфейса, вследствие которого экранный диктор произносит текст, предоставленный с событием, причем соответствующий элемент управления в пользовательском интерфейсе не требуется. В некоторых случаях это очень простой способ радикально улучшить доступность приложения. Он также может быть полезен для уведомления о ходе выполнения длительного процесса. Дополнительные сведения о событиях уведомлений в модели автоматизации пользовательского интерфейса Microsoft Windows см. в записи блога [Can your desktop app leverage the new UI Notification event?](https://blogs.msdn.microsoft.com/winuiautomation/2017/11/08/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need/) (Может ли ваше классическое приложение использовать новое событие уведомления пользовательского интерфейса?).

В следующем примере создается [событие уведомления](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

**Подсказки при доступе с клавиатуры**

В приложениях для платформы .NET Framework 4.7.2 и более ранних версий [подсказка](xref:System.Windows.Forms.ToolTip) элемента управления всплывает только при наведении на элемент указателя мыши. Начиная с .NET Framework 4.8 подсказка также может всплывать, когда пользователь переводит фокус на элемент управления с помощью клавиши TAB или клавиш со стрелками с клавишами-модификаторами или без них. Для данного улучшения специальных возможностей требуется дополнительный [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):

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

На изображении ниже показана подсказка, появляющаяся, когда пользователь выбирает кнопку с помощью клавиатуры.

![Подсказка, появляющаяся, когда пользователь переходит к кнопке с помощью клавиатуры](./media/tooltip.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Начиная с .NET Framework 4.8 в WPF внесен ряд улучшений специальных возможностей.

**Экранные дикторы больше не объявляют элементы с состоянием видимости Collapsed или Hidden**

Свернутые или скрытые элементы больше не объявляются средством чтения с экрана. Если элементы, свойство Visibility которых имеет значение <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> или <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType>, объявляются средством чтения с экрана, пользователь может получать неправильное представление о пользовательском интерфейсе. Начиная с .NET Framework 4.8 в WPF свернутые или скрытые элементы больше не включаются в представление элементов управления дерева UIAutomation, поэтому средства чтения с экрана больше не могут объявлять их.

**Свойство SelectionTextBrush для выделения текста без использования декоративного элемента**

В .NET Framework 4.7.2 в WPF появилась возможность отрисовывать выделение текста в <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> без использования слоя декоративных элементов. В таком случае цвет переднего плана выделенного текста определялся свойством <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.

В .NET Framework 4.8 добавлено новое свойство `SelectionTextBrush`, которое позволяет разработчикам выбирать кисть для текста, выделенного без использования декоративного элемента. Это свойство работает только для элементов управления, производных от <xref:System.Windows.Controls.Primitives.TextBoxBase>, и элемента управления <xref:System.Windows.Controls.PasswordBox> в приложениях WPF с включенным выделением текста без использования декоративного элемента. Оно не поддерживается элементом управления <xref:System.Windows.Controls.RichTextBox>. Если выделение текста без использования декоративного элемента не включено, это свойство игнорируется.

Чтобы использовать это свойство, просто добавьте его в код XAML и примените соответствующую кисть или привязку. В итоге выделенный текст выглядит так:

![Подсказка, появляющаяся, когда пользователь переходит к кнопке с помощью клавиатуры](./media/selectiontextbrush-property.png)

Свойства `SelectionBrush` и `SelectionTextBrush` можно использовать вместе, чтобы получить любую требуемую комбинацию цветов фона и переднего плана.

**Поддержка свойства ControllerFor в модели автоматизации пользовательского интерфейса Microsoft Windows**

Свойство `ControllerFor` в модели автоматизации пользовательского интерфейса Microsoft Windows возвращает массив элементов автоматизации, которые управляются элементом автоматизации, поддерживающим это свойство. Это свойство обычно используется для специальной возможности автозаполнения. Свойство `ControllerFor` применяется, когда элемент автоматизации влияет на одну или несколько частей пользовательского интерфейса приложения или рабочего стола. В противном случае влияние работы элемента управления сложно связать с элементами пользовательского интерфейса. Эта возможность позволяет элементам управления предоставлять значение для свойства `ControllerFor`.

В .NET Framework 4.8 появился новый виртуальный метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>. Чтобы предоставить значение для свойства `ControllerFor`, просто переопределите этот метод так, чтобы он возвращал `List<AutomationPeer>` для элементов управления, которыми управляет данный объект <xref:System.Windows.Automation.Peers.AutomationPeer>:

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

**Подсказки при доступе с клавиатуры**

В .NET Framework 4.7.2 и более ранних версиях подсказки отображались только при наведении указателя мыши на элемент управления. В .NET Framework 4.8 они также появляются при наведении фокуса с помощью клавиатуры, в том числе с помощью сочетаний клавиш.

Для использования этой возможности приложение должно быть предназначено для .NET Framework 4.8 или согласиться на ее использование с помощью параметров [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` и `Switch.UseLegacyToolTipDisplay`. Вот пример файла конфигурации приложения:

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

После включения этой возможности подсказки будут появляться при наведении фокуса с помощью клавиатуры для всех элементов управления, имеющих подсказки. Подсказка может пропадать через некоторое время или при смене фокуса. Пользователи также могут скрывать подсказки вручную с помощью нового сочетания клавиш CTRL+SHIFT+F10. После закрытия подсказки ее можно отобразить снова с помощью этого же сочетания клавиш.

> [!NOTE]
> [Подсказки на ленте](xref:System.Windows.Controls.Ribbon.RibbonToolTip) для элементов управления <xref:System.Windows.Controls.Ribbon.Ribbon> не появляются при наведении фокуса с помощью клавиатуры. Они отображаются только при использовании сочетания клавиш.

**Добавлена поддержка свойств SizeOfSet и PositionInSet в модели автоматизации пользовательского интерфейса Microsoft Windows**

В Windows 10 появились два новых свойства модели автоматизации пользовательского интерфейса Microsoft Windows: `SizeOfSet` и `PositionInSet`. Они используются приложениями для указания количества элементов в наборе. Клиентские приложения модели автоматизации пользовательского интерфейса Microsoft Windows, такие как средства чтения с экрана, могут запрашивать эти свойства, чтобы точно представлять пользовательский интерфейс приложения.

Начиная с .NET Framework 4.8 приложения WPF предоставляют доступ к этим двум свойствам модели автоматизации пользовательского интерфейса Microsoft Windows. Это можно сделать двумя способами:

- С помощью свойств зависимостей.

  В WPF добавлены два новых свойства зависимостей: <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>. Разработчик может задавать их значения с помощью XAML:

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- Путем переопределения виртуальных методов AutomationPeer.

  В класс AutomationPeer добавлены виртуальные методы <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore>. Разработчик может указывать значения для `SizeOfSet` и `PositionInSet`, переопределяя эти методы, как показано в следующем примере:

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

Кроме того, элементы в экземплярах <xref:System.Windows.Controls.ItemsControl> предоставляют значения для этих свойств автоматически. Разработчику делать это не требуется. Если экземпляр <xref:System.Windows.Controls.ItemsControl> сгруппирован, коллекция групп представлена как набор. Каждая группа считается отдельным набором, а каждый элемент в группе указывает свое положение в ней, а также размер группы. Виртуализация не влияет на автоматически задаваемые значения. Даже если элемент не реализован, он по-прежнему учитывается при определении общего размера набора и влияет на положение других элементов в наборе.

Значения предоставляются автоматически, только если приложение предназначено для .NET Framework 4.8. Если приложение предназначено для более ранних версий .NET Framework, можно задать [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3`, как показано в следующем файле App.config:

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

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Конструктор рабочих процессов Windows Workflow Foundation (WF)

В конструктор рабочих процессов в .NET Framework 4.8 внесены указанные ниже изменения.

- Улучшены метки case FlowSwitch при использовании экранного диктора.

- Улучшены описания кнопок при использовании экранного диктора.

- Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.

Если приложение предназначено для .NET Framework 4.7.2 или более ранней версии, эти улучшения можно активировать отдельно, установив [параметр AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.UseLegacyAccessibilityFeatures.3` в значение `false` в файле конфигурации приложения. Дополнительные сведения см. в разделе [Использование преимуществ усовершенствованных специальных возможностей](#taking-advantage-of-accessibility-enhancements) этой статьи.

## <a name="whats-new-in-accessibility-in-net-framework-472"></a>Улучшения специальных возможностей в .NET Framework 4.7.2

Платформа .NET Framework 4.7.2 включает новые функции специальных возможностей в следующих областях:

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

Начиная с .NET Framework 4.7.2 усовершенствована поддержка экранного диктора:

- Он сообщает значение свойства <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> при объявлении текста <xref:System.Windows.Forms.ToolStripMenuItem>.

- Он указывает, когда для свойства <xref:System.Windows.Forms.Control.Enabled> элемента <xref:System.Windows.Forms.ToolStripMenuItem> задано значение `false`.

- Он предоставляет отзыв о состоянии флажка, если для свойства <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> задано значение `true`.

- Порядок фокуса экранного диктора в режиме сканирования согласуется с визуальным порядком элементов управления в диалоговом окне загрузки ClickOnce.

**Усовершенствования DataGridView**

Начиная с .NET Framework 4.7.2 элемент управления <xref:System.Windows.Forms.DataGridView> вносит следующие улучшения специальных возможностей:

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

В .NET Framework 4.7.1 и более ранних версий элементы управления <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> и <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> WPF имеют несогласованные и (в классической теме и теме высокой контрастности) неправильные визуальные элементы фокуса.  Это происходит в случаях, когда для элементов управления не задано какое-либо содержимое.  Это может затруднять переход между темами и отображение визуального элемента фокуса.

В .NET Framework 4.7.2 эти визуальные элементы стали более согласованными в разных темах и более видимыми в классической и контрастной темах.

**Элементы управления WinForms, размещенные в приложении WPF**

При использовании элемента управления WinForms, размещенного в приложении WPF в .NET Framework 4.7.1 и более ранних версий, пользователи не могли выйти из слоя WinForms с помощью клавиши табуляции, если первый или последний элемент управления в слое был элементом управления <xref:System.Windows.Forms.Integration.ElementHost> WPF. В .NET Framework 4.7.2 пользователи теперь могут выйти из слоя WinForms с помощью клавиши табуляции.

Однако автоматизированные приложения, которые зависят от постоянного нахождения фокуса в слое WinForms, могут работать некорректно.

## <a name="whats-new-in-accessibility-in-net-framework-471"></a>Улучшения специальных возможностей в .NET Framework 4.7.1

Платформа .NET Framework 4.7.1 включает новые функции специальных возможностей в следующих областях:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [Веб-элементы управления ASP.NET](#aspnet471)

- [.NET SDK Tools](#tools471)

- [Конструктор рабочих процессов Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Улучшения средств чтения с экрана**

Если включены улучшения специальных возможностей, .NET Framework 4.7.1 содержит следующие усовершенствования, касающиеся средств чтения с экрана:

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.Expander> объявлялись средствами чтения с экрана как кнопки. Начиная с .NET Framework 4.7.1 они правильно объявляются как развертываемые и свертываемые группы.

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.DataGridCell> объявлялись средствами чтения с экрана как пользовательские. Начиная с .NET Framework 4.7.1 они правильно объявляются как ячейка сетки данных (локализованная).

- Начиная с .NET Framework 4.7.1 средства чтения с экрана объявляют имя изменяемого <xref:System.Windows.Controls.ComboBox>.

- В .NET Framework 4.7 и более ранних версий элементы управления <xref:System.Windows.Controls.PasswordBox> объявлялись как "в представлении нет элементов" или имели иное неправильное поведение. Начиная с .NET Framework 4.7.1 эта проблема устранена.

**Поддержка динамических областей автоматизации пользовательского интерфейса**

Средства чтения с экрана, такие как экранный диктор, помогают людям читать содержимое пользовательского интерфейса приложения. Обычно для этого используется преобразование текста в речь для содержимого, находящегося в фокусе. Однако если элемент пользовательского интерфейса изменяется и находится не в фокусе, пользователь может не получить уведомление и пропустить важные сведения. Динамические области призваны решить эту проблему. Разработчик может использовать их для информирования средства чтения с экрана или любого другого клиента автоматизации пользовательского интерфейса о важных изменениях элемента пользовательского интерфейса. После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении.

Для поддержки динамических областей в WPF добавлены следующие API:

- Поля <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>, которые идентифицируют свойство **LiveSetting** и событие **LiveRegionChanged**. Их можно задать с помощью XAML.

- Присоединенное свойство **AutomationProperties.LiveSetting**, уведомляющее средство чтения с экрана о том, насколько важно изменение пользовательского интерфейса для пользователя.

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

Начиная с .NET Framework 4.7.1 внесены улучшения в функции высокой контрастности для различных элементов управления WPF. Теперь они видны, когда задана тема <xref:System.Windows.SystemParameters.HighContrast%2A>. Сюда входит следующее.

- Элемент управления <xref:System.Windows.Controls.Expander>

  Визуальный элемент фокуса для элемента управления <xref:System.Windows.Controls.Expander> теперь отображается. Визуальные элементы клавиатуры для элементов управления <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.RadioButton> также видимы. Например:

  До: 

  ![Элемент управления Expander с фокусом до внесения улучшений](./media/expander-before.png)

  После: 

  ![Элемент управления Expander с фокусом после внесения улучшений](./media/expander-after.png)

- Элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton>

  Текст в элементах управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> теперь стало проще читать, когда он выбран при использовании тем с высокой контрастностью. Например:

  До: 

  ![Переключатель высокой контрастности до внесения улучшений](./media/radio-button-before.png)

  После: 

  ![Переключатель высокой контрастности после внесения улучшений](./media/radio-button-after.png)

- Элемент управления <xref:System.Windows.Controls.ComboBox>

  Начиная с .NET Framework 4.7.1 граница отключенного элемента управления <xref:System.Windows.Controls.ComboBox> имеет цвет отключенного текста. Например:

  До: 

  ![Отключенная граница и текст поля со списком до внесения улучшений](./media/combo-disabled-before.png)

  После:   

  ![Отключенная граница и текст поля со списком после внесения улучшений](./media/combo-disabled-after.png)

  Кроме того, отключенные и находящиеся в фокусе кнопки используют правильный цвет темы.

  До:

  ![Цвета темы для кнопок до внесения улучшений](./media/button-themes-before.png) 

  После: 

  ![Цвета темы для кнопок после внесения улучшений](./media/button-themes-after.png) 

  Наконец, в .NET Framework 4.7 и более ранних версий установка стиля элемента управления <xref:System.Windows.Controls.ComboBox> в значение `Toolbar.ComboBoxStyleKey` приводила к тому, что стрелка раскрывающегося списка была невидимой. Начиная с .NET Framework 4.7.1 эта проблема устранена. Например:

  До: 

  ![Toolbar.ComboBoxStyleKey до внесения улучшений](./media/comboboxstylekey-before.png) 

  После: 

  ![Toolbar.ComboBoxStyleKey после внесения улучшений](./media/comboboxstylekey-after.png) 

- Элемент управления <xref:System.Windows.Controls.DataGrid>

  Начиная с .NET Framework 4.7.1 стрелка индикатора сортировки в элементе управления <xref:System.Windows.Controls.DataGrid> имеет правильные цвета темы. Например:

  До: 

  ![Стрелка индикатора сортировки до внесения улучшений](./media/sort-indicator-before.png) 

  После:   

  ![Стрелка индикатора сортировки после внесения улучшений](./media/sort-indicator-after.png) 

  Кроме того, в .NET Framework 4.7 и более ранних версий стиль ссылки по умолчанию изменялся на неправильный цвет при наведении указателя мыши в режимах высокой контрастности. Начиная с .NET Framework 4.7.1 эта проблема устранена. Аналогичным образом, столбец флажка <xref:System.Windows.Controls.DataGrid> использует ожидаемые цвета для отзывов на фокус клавиатуры начиная с .NET Framework 4.7.1.

  До: 

  ![Стиль ссылки по умолчанию DataGrid до внесения улучшений](./media/default-link-style-before.png) 

  После:    

  ![Стиль ссылки по умолчанию DataGrid после внесения улучшений](./media/default-link-style-after.png) 

Дополнительные сведения об улучшениях специальных возможностей WPF в .NET Framework 4.7.1 см. в разделе [Улучшения специальных возможностей в WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Улучшения специальных возможностей в Windows Forms

В модель Windows Forms (WinForms) платформы .NET Framework 4.7.1 были внесены изменения специальных возможностей в следующих областях:

**Улучшенное отображение в режиме высокой контрастности**

Начиная с .NET Framework 4.7.1 различные элементы управления WinForms обеспечивают улучшенную отрисовку в режимах высокой контрастности, доступных в операционной системе. В Windows 10 были изменены некоторые системные цвета в режиме высокой контрастности, а Windows Forms основан на платформе Win32 Windows 10. Для достижения наилучших результатов используйте самую последнюю версию Windows и согласитесь на последние изменения операционной системы, добавив файл app.manifest в тестовое приложение и раскомментировав строку поддержки Windows 10, чтобы она выглядела следующим образом:

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

Некоторые примеры изменения режима высокой контрастности:

- Лучше читаются флажки в элементах <xref:System.Windows.Forms.MenuStrip>.

- Лучше читаются выбранные отключенные элементы <xref:System.Windows.Forms.MenuStrip>.

- Текст в выбранном <xref:System.Windows.Forms.Button> элементе управления отличается от цвета выбора.

- Отключенный текст проще читать. Например:

  До:

  ![Отключенный текст до внесения улучшений](./media/wf-disabled-before.png) 

  После:

  ![Отключенный текст после внесения улучшений](./media/wf-disabled-after.png) 

- Усовершенствования режима высокой контрастности в диалоговом окне исключения потока.

**Улучшенная поддержка экранного диктора**

Модель Windows Forms в .NET Framework 4.7.1 содержит следующие улучшения специальных возможностей для экранного диктора:

- К элементу управления <xref:System.Windows.Forms.MonthCalendar> может обратиться как экранный диктор, так и любое другое средство автоматизации пользовательского интерфейса.

- Элемент управления <xref:System.Windows.Forms.CheckedListBox> оповещает экранный диктор об изменении состояния флажка элемента, чтобы пользователь узнал, что значение элемента списка изменилось.

- Элемент управления <xref:System.Windows.Forms.DataGridViewCell> сообщает правильное состояние доступа только для чтения экранному диктору.

- Теперь экранный диктор может прочитать отключенный текст <xref:System.Windows.Forms.ToolStripMenuItem>, хотя раньше он пропускал отключенные пункты меню.

**Улучшенная поддержка шаблонов специальных возможностей автоматизации пользовательского интерфейса**

Начиная с .NET Framework 4.7.1 разработчики средств специальных возможностей могут использовать стандартные шаблоны специальных возможностей API и свойства для нескольких элементов управления WinForms. Некоторые из этих улучшений специальных возможностей:

- <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ToolStripSplitButton> теперь поддерживают [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> теперь поддерживает [шаблон переключения](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).

- Элемент управления <xref:System.Windows.Forms.ToolStripItem> поддерживает свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> и [шаблон развертывания/свертывания](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Элементы управления <xref:System.Windows.Forms.NumericUpDown> и <xref:System.Windows.Forms.DomainUpDown> поддерживают свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.

**Улучшенное взаимодействие с обозревателем свойств**

Начиная с .NET Framework 4.7.1 модель Windows Forms включает в себя следующее:

- Улучшенная навигация с помощью клавиатуры посредством различных окон выбора с раскрывающимися списками.
- Сокращение ненужных позиций табуляции.
- Улучшенные отчеты о типах элементов управления.
- Улучшенная работа экранного диктора.

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a>Веб-элементы управления ASP.NET

Начиная с .NET Framework 4.7.1 и Visual Studio 2017 версии 15.3 в ASP.NET улучшена работа веб-элементов управления ASP.NET с технологией специальных возможностей в Visual Studio. Внесены следующие изменения:

- Изменения для реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления, например в диалоговом окне **Добавить поле** в мастере **представления сведений** или в диалоговом окне **Настройка ListView** в мастере **ListView**.

- Изменения для улучшенного отображения в режиме высокой контрастности, например в **редакторе полей страничного навигатора данных**.

- Изменения для улучшения навигации с помощью клавиатуры для таких элементов, как диалоговое окно **Поля** в мастере **полей страничного навигатора**, диалоговое окно **Настроить ObjectContext** или **Настроить выбор данных** в мастере **настройки источника данных**.

<a name="tools471"></a>

### <a name="net-sdk-tools"></a>.NET SDK Tools

В [редакторе конфигурации (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) и [средстве Service Trace Viewer (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) были устранены различные ошибки специальных возможностей. В основном это были незначительные проблемы, например не определялось имя или некорректно реализовывались шаблоны автоматизации пользовательского интерфейса. Многие пользователи могли не замечать неверные значения, но пользователям, использующим вспомогательные технологии, такие как средства чтения с экрана, будет проще использовать эти средства пакета SDK.

Эти усовершенствования меняют предыдущее поведение, например порядок фокуса клавиатуры.

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Конструктор рабочих процессов Windows Workflow Foundation (WF)

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

- [Новые возможности .NET Framework](index.md)
