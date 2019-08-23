---
title: Windows Forms добавить элемент конфигурации
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb607af0933ea64b7d67f8ed082ffce6e7d21f51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913064"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms добавить элемент конфигурации

`<add>` Элемент добавляет предопределенный ключ, указывающий, поддерживает ли приложение Windows Form функции, добавленные в Windows Forms приложения в .NET Framework 4,7 или более поздней версии.

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
| `value`   | Обязательный атрибут. Присваиваемое значение `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`имена атрибутов и связанные значения

| `key`безымян | Значения | Описание |
| ---------- | ------ | ----------- |
| "Анчорлайаут. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли привязанные элементы управления за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "Дпиаваренесс" | "PerMonitorV2"&#124;"false" | Указывает, учитывается ли в приложении разрешение DPI. Задайте для ключа значение "PerMonitorV2", чтобы обеспечить поддержку отслеживания dpi. в противном случае задайте для него значение "false". Поддержка DPI является функцией согласия; чтобы воспользоваться преимуществами Windows Forms "поддержка высокого DPI", следует присвоить ей значение "PerMonitorV2". Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| CheckedListBox. Дисаблехигхдпиимпровементс | "true"&#124;"false" | Указывает, использует <xref:System.Windows.Forms.CheckedListBox> ли элемент управления преимущества масштабирования и улучшения макета, представленные в .NET Framework 4,7. значение true, чтобы отказаться от улучшений масштабирования и макета; в противном случае — значение false. |
| "DataGridView. Дисаблехигхдпиимпровементс" | "true"&#124;"false" | Указывает, <xref:System.Windows.Forms.DataGridView> появились ли улучшения масштабирования и разметки элемента управления в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |
| "Дисабледпичанжедмессажехандлинг" | "true"&#124;"false" | значение true, чтобы отказаться от получения сообщений, связанных с изменениями масштабирования DPI; в противном случае — значение false. Дополнительные сведения см. в разделе ["Примечания"](#remarks) . |
| "Енаблевиндовсформшигхдпиауторесизинг" | "true"&#124;"false" | Указывает, изменяется ли размер приложения Windows Forms автоматически из-за изменения масштабирования DPI. значение true, чтобы включить автоматическое изменение размера; в противном случае — значение false. |
| "Form. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли объект <xref:System.Windows.Forms.Form> за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "MonthCalendar. Дисаблесинглепассконтролскалинг" | "true"&#124;"false" | Указывает, масштабируется ли <xref:System.Windows.Forms.MonthCalendar> элемент управления за один проход. значение true, чтобы отключить однопроходное масштабирование; в противном случае — значение false. Дополнительные сведения см. в подразделе "однопроходное масштабирование" в [примечаниях](#remarks) . |
| "ToolStrip. Дисаблехигхдпиимпровементс" | "true"&#124;"false" | Указывает, использует <xref:System.Windows.Forms.ToolStrip> ли элемент управления преимущества масштабирования и улучшения макета, представленные в .NET Framework 4,7. значение true, чтобы отказаться от осведомленности о DPI; в противном случае — значение false. |

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Настраивает поддержку новых функций приложения Windows Forms. |

## <a name="remarks"></a>Примечания

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework.

Элемент позволяет добавить один или несколько дочерних `<add>` элементов, каждый из которых определяет конкретный параметр конфигурации. `<System.Windows.Forms.ApplicationConfigurationSection>`

Общие сведения о поддержке Windows Forms высокого DPI см. [в разделе Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>дпиаваренесс

Windows Forms приложения, работающие под управлением версий Windows, начиная с версии Windows 10 Creators Edition и целевой версии .NET Framework, начиная с .NET Framework 4,7, можно настроить на использование преимуществ улучшенных точек на дюйм, появившихся в .NET Framework 4,7. Сюда входит следующее.

- Поддержка сценариев динамического МАСШТАБИРОВАНИЯ, при которой пользователь изменяет значение DPI или коэффициент масштабирования после запуска Windows Forms приложения.

- Улучшения в масштабировании и компоновке ряда элементов управления Windows Forms, таких как <xref:System.Windows.Forms.MonthCalendar> элемент управления <xref:System.Windows.Forms.CheckedListBox> и элемент управления.

Поддержка высокого DPI является функцией согласия. по умолчанию значение `DpiAwareness` равно `false`. Вы можете включить поддержку Windows Forms "для отслеживания dpi, задав для `PerMonitorV2` этого ключа значение в файле конфигурации приложения. Если включена поддержка DPI, также включаются все индивидуальные функции DPI. Сюда входит следующее.

- Измененные сообщения dpi, управляемые `DisableDpiChangedMessageHandling` ключом.

- Поддержка динамического dpi, управляемая `EnableWindowsFormsHighDpiAutoResizing` ключом.

- Масштабирование элемента управления с `Form.DisableSinglePassControlScaling` одним проходом, которое управляется для отдельных <xref:System.Windows.Forms.Form> элементов управления, `AnchorLayout.DisableSinglePassControlScaling` ключом `MonthCalendar.DisableSinglePassControlScaling` для привязанных <xref:System.Windows.Forms.MonthCalendar> элементов управления и ключом для элемента управления.

- `CheckListBox.DisableHighDpiImprovements` Улучшенное масштабирование и улучшение макета, которые управляются ключом <xref:System.Windows.Forms.CheckedListBox> `Toolstrip.DisableHighDpiImprovements` `DataGridView.DisableHighDpiImprovements` элемента управления, ключом для <xref:System.Windows.Forms.DataGridView> элемента управления и ключом для <xref:System.Windows.Forms.ToolStrip> элемента управления.

Параметр одиночного согласия по умолчанию, предоставляемый `DpiAwareness` параметром `PerMonitorV2` , обычно подходит для новых Windows Forms приложений. Однако можно отказаться от отдельных улучшений с высоким разрешением, добавив соответствующий ключ в файл конфигурации приложения. Например, чтобы воспользоваться преимуществами всех новых функций DPI, за исключением динамической поддержки DPI, добавьте в файл конфигурации приложения следующее:

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

Начиная с .NET Framework 4,7, элементы управления Windows Forms создают ряд событий, связанных с изменениями масштабирования DPI. К <xref:System.Windows.Forms.Control.DpiChangedAfterParent>ним относятся события <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, и <xref:System.Windows.Forms.Form.DpiChanged> . Значение `DisableDpiChangedMessageHandling` ключа определяет, возникают ли эти события в Windows Forms приложении.

### <a name="single-pass-scaling"></a>Однопроходное масштабирование

Масштабирование одного или нескольких потоков влияет на скорость реагирования пользовательского интерфейса и визуальный внешний вид элементов пользовательского интерфейса по мере их масштабирования. Начиная с .NET Framework 4,7, Windows Forms использует однопроходное масштабирование. В предыдущих версиях .NET Framework масштабирование выполнялось с помощью нескольких проходов, что привело к увеличению количества элементов управления, чем требовалось. Если приложение зависит от старого поведения, необходимо отключить однопроходное масштабирование.

## <a name="see-also"></a>См. также

- [Раздел конфигурации Windows Forms](index.md)
- [Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
