---
title: Windows Forms добавить элемент конфигурации
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
ms.openlocfilehash: 26b806f84c3e1bc44e0437a8f8806316b14897b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109665"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms добавить элемент конфигурации

Элемент `<add>` добавляет предопределенный ключ, указывающий, поддерживает ли приложение Windows Form функции, добавленные в Windows Forms приложения в .NET Framework 4,7 или более поздней версии.

## <a name="syntax"></a>Синтаксис

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

| Атрибут | Описание |
| --------- | ----------- |
| `key`     | Обязательный атрибут. Предопределенное имя ключа, соответствующее определенной Windows Forms настраиваемой функции. |
| `value`   | Обязательный атрибут. Значение, присваиваемое `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` имена атрибутов и связанные значения

| Имя в `key` | Значения | Описание |
| ---------- | ------ | ----------- |
| "Анчорлайаут. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли привязанные элементы управления за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "Дпиаваренесс" | "PerMonitorV2"&#124;"false" | Указывает, учитывается ли в приложении разрешение DPI. Задайте для ключа значение "PerMonitorV2", чтобы обеспечить поддержку отслеживания dpi. в противном случае задайте для него значение "false". Поддержка DPI является функцией согласия; чтобы воспользоваться преимуществами Windows Forms "поддержка высокого DPI", следует присвоить ей значение "PerMonitorV2". Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| CheckedListBox. Дисаблехигхдпиимпровементс | "true"&#124;"false" | Указывает, использует ли элемент управления <xref:System.Windows.Forms.CheckedListBox> преимущества масштабирования и улучшений макета, появившихся в .NET Framework 4,7. значение true, чтобы отказаться от улучшений масштабирования и макета; в противном случае — значение false. |
| "DataGridView. Дисаблехигхдпиимпровементс" | "true"&#124;"false" | Указывает, появились ли улучшения масштабирования и разметки элемента управления <xref:System.Windows.Forms.DataGridView>, появившиеся в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |
| "Дисабледпичанжедмессажехандлинг" | "true"&#124;"false" | значение true, чтобы отказаться от получения сообщений, связанных с изменениями масштабирования DPI; в противном случае — значение false. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| "Енаблевиндовсформшигхдпиауторесизинг" | "true"&#124;"false" | Указывает, изменяется ли размер приложения Windows Forms автоматически из-за изменения масштабирования DPI. значение true, чтобы включить автоматическое изменение размера; в противном случае — значение false. |
| "Form. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли <xref:System.Windows.Forms.Form> за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "MonthCalendar. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли элемент управления <xref:System.Windows.Forms.MonthCalendar> в течение одного прохода. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "ToolStrip. Дисаблехигхдпиимпровементс" | "true"&#124;"false" | Указывает, использует ли элемент управления <xref:System.Windows.Forms.ToolStrip> преимущества масштабирования и улучшений макета, появившихся в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Настраивает поддержку новых функций приложения Windows Forms. |

## <a name="remarks"></a>Заметки

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.

Элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет добавить один или несколько дочерних элементов `<add>`, каждый из которых определяет конкретный параметр конфигурации.

Общие сведения о поддержке Windows Forms высокого DPI см. [в разделе Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>дпиаваренесс

Windows Forms приложения, работающие под управлением версий Windows, начиная с версии Windows 10 Creators Edition и целевой версии .NET Framework, начиная с .NET Framework 4,7, можно настроить на использование преимуществ улучшенных точек на дюйм, появившихся в .NET Framework 4,7. Сюда входит следующее.

- Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.

- Улучшения в масштабировании и компоновке нескольких элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления и элемент управления <xref:System.Windows.Forms.CheckedListBox>.

Поддержка высокого DPI является функцией согласия. по умолчанию значением `DpiAwareness` является `false`. Вы можете включить поддержку Windows Forms "для отслеживания DPI, установив значение этого параметра равным `PerMonitorV2` в файле конфигурации приложения. Если включена поддержка DPI, также включаются все индивидуальные функции DPI. Сюда входит следующее.

- Сообщения, измененные DPI, управляются ключом `DisableDpiChangedMessageHandling`.

- Поддержка динамических точек на дюйм, которая управляется ключом `EnableWindowsFormsHighDpiAutoResizing`.

- Масштабирование управления с одним проходом, которое управляется `Form.DisableSinglePassControlScaling` для отдельных элементов управления <xref:System.Windows.Forms.Form>, ключом `AnchorLayout.DisableSinglePassControlScaling` для привязанных элементов управления и ключом `MonthCalendar.DisableSinglePassControlScaling` для элемента управления <xref:System.Windows.Forms.MonthCalendar>

- Улучшенное масштабирование и улучшение макета, которые управляются ключом `CheckListBox.DisableHighDpiImprovements` для элемента управления <xref:System.Windows.Forms.CheckedListBox>, ключом `DataGridView.DisableHighDpiImprovements` для элемента управления <xref:System.Windows.Forms.DataGridView> и ключом `Toolstrip.DisableHighDpiImprovements` для элемента управления <xref:System.Windows.Forms.ToolStrip>.

Параметр одиночного согласия по умолчанию, предоставляемый параметром `DpiAwareness` `PerMonitorV2`, обычно подходит для новых Windows Forms приложений. Однако можно отказаться от отдельных улучшений с высоким разрешением, добавив соответствующий ключ в файл конфигурации приложения. Например, чтобы воспользоваться преимуществами всех новых функций DPI, за исключением динамической поддержки DPI, добавьте в файл конфигурации приложения следующее:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Как правило, вы отказываетесь от конкретной функции, так как вы решили управлять ею программным способом.

Дополнительные сведения о поддержке высокого DPI в Windows Forms приложениях см. [в разделе Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>дисабледпичанжедмессажехандлинг

Начиная с .NET Framework 4,7, элементы управления Windows Forms создают ряд событий, связанных с изменениями масштабирования DPI. К ним относятся события <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>и <xref:System.Windows.Forms.Form.DpiChanged>. Значение ключа `DisableDpiChangedMessageHandling` определяет, вызываются ли эти события в приложении Windows Forms.

### <a name="single-pass-scaling"></a>Однопроходное масштабирование

Масштабирование одного или нескольких потоков влияет на скорость реагирования пользовательского интерфейса и визуальный внешний вид элементов пользовательского интерфейса по мере их масштабирования. Начиная с .NET Framework 4,7, Windows Forms использует однопроходное масштабирование. В предыдущих версиях .NET Framework масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось. Если приложение зависит от старого поведения, необходимо отключить однопроходное масштабирование.

## <a name="see-also"></a>См. также

- [Раздел конфигурации Windows Forms](index.md)
- [Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
