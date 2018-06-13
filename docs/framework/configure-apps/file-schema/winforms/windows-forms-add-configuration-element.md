---
title: Windows Forms добавьте элемент конфигурации
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529dbccd5ddb4dd1f1456fb9a6043f3c5f7b378d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759664"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms добавьте элемент конфигурации

`<add>` Элемент добавляет стандартный раздел, указывающее, поддерживает ли приложение Windows Form, добавленных в приложениях Windows Forms в .NET Framework 4.7 или более поздней версии.

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
| `key`     | Обязательный атрибут. Предопределенные имя ключа, соответствующий конкретной настраиваемые функции Windows Forms. |
| `value`   | Обязательный атрибут. Значение, присваиваемое `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` имена атрибутов и связанных значений

| Имя в `key` | Значения | Описание |
| ---------- | ------ | ----------- |
| «AnchorLayout.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, являются ли привязанные элементы управления масштабируется за один проход. «true», чтобы отключить один передать масштабирования; в противном случае — значение false. В разделе «Передать одним масштабирование» в [примечания](#Remarks) для получения дополнительной информации. |
| «DpiAwareness» | «PerMonitorV2»&#124;«false» | Указывает, является ли приложение как поддерживающее DPI. Ключ «PerMonitorV2» для поддержки сведения о состоянии точек на дюйм; противном случае задайте значение «false». Поддержка точек на ДЮЙМ является функция, включаемая; Чтобы воспользоваться преимуществами высоким DPI поддержки Windows Forms, следует присвойте ему значение «PerMonitorV2». В разделе [примечания](#remarks) Дополнительные сведения. |
| «CheckedListBox.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.CheckedListBox> управления использует преимущества масштабирования и макет усовершенствования, появившиеся в .NET Framework 4.7. «true», чтобы отказаться от улучшения caling и макет; в противном случае — значение «false». |
| «DataGridView.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.DataGridView> управления масштабирования и макет усовершенствования, появившиеся в .NET Framework 4.7. «true», чтобы отказаться от сведения о состоянии точек на ДЮЙМ; «false» в противном случае. |
| «DisableDpiChangedMessageHandling» | «true»&#124;«false» | «true», чтобы отказаться от получения сообщений, связанных с разрешение DPI изменения; «false» в противном случае. В разделе [примечания](#remarks) Дополнительные сведения. |
| «EnableWindowsFormsHighDpiAutoResizing» | «true»&#124;«false» | Указывает, изменяется ли автоматически приложения Windows Forms из-за изменения масштабирования точек на ДЮЙМ. «true», чтобы включить автоматическое изменение размеров; в противном случае — значение false. |
| «Form.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.Form> масштабируется за один проход. «true», чтобы отключить один проход масштабирования; в противном случае — значение false. В разделе «Передать одним масштабирование» в [примечания](#Remarks) для получения дополнительной информации. |
| «MonthCalendar.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.MonthCalendar> масштабируется элемент управления за один проход. «true», чтобы отключить один проход масштабирования; в противном случае — значение false. В разделе «Передать одним масштабирование» в [примечания](#Remarks) для получения дополнительной информации. |
| «Toolstrip.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.ToolStrip> управления использует преимущества масштабирования и макет усовершенствования, появившиеся в .NET Framework 4.7. «true», чтобы отказаться от сведения о состоянии точек на ДЮЙМ; «false» в противном случае. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Настройка поддержки для новых функций приложения Windows Forms. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> Примечания

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework. 

`<System.Windows.Forms.ApplicationConfigurationSection>` Элемента можно добавить один или несколько дочерних `<add>` элементов, каждый из которых определяет параметр конкретной конфигурации.  

Обзор поддержка высокого Разрешения Windows Forms см. в разделе [высокий уровень поддержки DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Приложения Windows Forms, выполняемых в версиях Windows, начиная с выпуска создатели Windows 10 и версий платформы .NET Framework, начиная с .NET Framework 4.7 можно настроить таким образом, чтобы воспользоваться преимуществами высокого уровня DPI усовершенствования, появившиеся в .NET Framework 4.7. Сюда входит следующее.

- Поддержка динамического DPI сценариев, в которых пользователь изменяет коэффициент DPI или масштаб после запуска приложения Windows Forms.

- Усовершенствования в масштабировании и макет несколько форм Windows элементы управления, такие как <xref:System.Windows.Forms.MonthCalendar> управления и <xref:System.Windows.Forms.CheckedListBox> элемента управления. 

Высокого уровня осведомленности точек на ДЮЙМ является дополнительной функции; по умолчанию значение `DpiAwareness` — `false`. Вы можете выбрать в Windows Forms поддержку для учета DPI, путем установки значения этого параметра для `PerMonitorV2` в файле конфигурации приложения. Если включена поддержка точек на ДЮЙМ, также включены все отдельные компоненты точек на ДЮЙМ. Сюда входит следующее.

- Точек на ДЮЙМ изменения сообщений, которые управляются `DisableDpiChangedMessageHandling` ключа.

- Динамические поддержки точек на ДЮЙМ, которая управляется `EnableWindowsFormsHighDpiAutoResizing` ключа.

- Одного прохода масштабирование элемента управления, который управляется `Form.DisableSinglePassControlScaling` для отдельных <xref:System.Windows.Forms.Form> управляет, путем `AnchorLayout.DisableSinglePassControlScaling` ключа по привязанные элементы управления и на `MonthCalendar.DisableSinglePassControlScaling` ключа для <xref:System.Windows.Forms.MonthCalendar> элемента управления 

- Высокая DPI масштабирование и макет улучшений, которые управляются `CheckListBox.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.CheckedListBox> управления по `DataGridView.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.DataGridView> управления и с помощью `Toolstrip.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.ToolStrip> элемента управления.  

Один участия в программе по умолчанию, предоставляемые параметр `DpiAwareness` для `PerMonitorV2` подходит для новых приложений Windows Forms. Тем не менее можно затем отказаться от отдельных высокий уровень улучшения точек на ДЮЙМ, добавив соответствующий раздел файла конфигурации приложения. Например чтобы использовать преимущества всех новых точек на ДЮЙМ featuers за исключением поддержки динамического DPI, необходимо добавить в файл конфигурации приложения следующие:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
Как правило отказаться от конкретных функциональных возможностей, так как вы выбрали программным путем его обработки.

Дополнительные сведения о преимуществ поддержка высокого Разрешения в приложениях Windows Forms см. в разделе [высокий уровень поддержки DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

Начиная с .NET Framework 4.7, элементы управления Windows Forms привести к возникновению ряда событий, связанных с изменениями в масштабирование. К ним относятся <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, и <xref:System.Windows.Forms.Form.DpiChanged> события. Значение `DisableDpiChangedMessageHandling` ключ определяет, является ли эти события вызываются в приложении Windows Forms. 

### <a name="single-pass-scaling"></a>Масштабирование одного прохода

Одной или несколькими pass Масштабирование влияет воспринимаемая пользователем скорость реагирования пользовательского интерфейса и внешний вид элементов пользовательского интерфейса, при увеличении масштаба. Начиная с .NET Framework 4.7, Windows Forms использует один проход масштабирования. В предыдущих версиях платформы .NET Framework масштабирования была выполнена через несколько проходов, которые вызвала некоторые элементы управления масштабировать больше, чем необходимо. Один проход масштабирование следует отключать только если приложение зависит от старого поведения.  

## <a name="see-also"></a>См. также
 
[Раздел конфигурации Windows Forms](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Поддержка высокого DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
