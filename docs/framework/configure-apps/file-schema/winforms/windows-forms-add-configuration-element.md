---
title: Windows Forms добавьте элемент конфигурации
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb0d058cd1ade65bfdc966819c0c41d9c1a9750
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185996"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms добавьте элемент конфигурации

`<add>` Элемент добавляет стандартный раздел, указывающее, поддерживает ли приложение форм Windows, добавленных в приложениях Windows Forms в .NET Framework 4.7 или более поздней версии.

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
| `key`     | Обязательный атрибут. Предопределенные имя ключа, которое соответствует определенный настраиваемый компонент Windows Forms. |
| `value`   | Обязательный атрибут. Значение, присваиваемое `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` имена атрибутов и связанных значений

| Имя в `key` | Значения | Описание |
| ---------- | ------ | ----------- |
| «AnchorLayout.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, являются ли привязанные элементы управления масштабируется за один проход. «true», чтобы отключить единый передать масштабирование; в противном случае — значение false. См. в разделе «Pass одним масштабирование» ["Примечания"](#Remarks) Дополнительные сведения. |
| «DpiAwareness» | «PerMonitorV2»&#124;«false» | Указывает, является ли приложение поддерживает определение DPI. Ключ «PerMonitorV2» для поддержки поддержка DPI; в противном случае ему присвоено значение «false». Поддержка DPI является дополнительной функции; Чтобы воспользоваться преимуществами поддержка высокого Разрешения Windows Forms, необходимо задать его значение для «PerMonitorV2». См. в разделе ["Примечания"](#remarks) Дополнительные сведения. |
| «CheckedListBox.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.CheckedListBox> элемент управления использует преимущества масштабирования и разметки улучшений, появившихся в .NET Framework 4.7. «true», чтобы отказаться от улучшения caling и макет; в противном случае — значение «false». |
| «DataGridView.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.DataGridView> управления масштабирования и разметки усовершенствования, появившиеся в .NET Framework 4.7. «true», чтобы отказаться от поддержки определения DPI; «false» в противном случае. |
| «DisableDpiChangedMessageHandling» | «true»&#124;«false» | «true», чтобы отказаться от получения сообщений, связанных с точек на ДЮЙМ, масштабирование изменения; «false» в противном случае. См. в разделе ["Примечания"](#remarks) Дополнительные сведения. |
| «EnableWindowsFormsHighDpiAutoResizing» | «true»&#124;«false» | Указывает, изменяется ли автоматически в приложении Windows Forms из-за изменений масштабирования точек на ДЮЙМ. «true», чтобы включить автоматическое изменение размера; в противном случае — значение false. |
| «Form.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.Form> масштабируется за один проход. «true», чтобы отключить однократного прохода масштабирование; в противном случае — значение false. См. в разделе «Pass одним масштабирование» ["Примечания"](#Remarks) Дополнительные сведения. |
| «MonthCalendar.DisableSinglePassControlScaling» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.MonthCalendar> масштабируется элемент управления за один проход. «true», чтобы отключить однократного прохода масштабирование; в противном случае — значение false. См. в разделе «Pass одним масштабирование» ["Примечания"](#Remarks) Дополнительные сведения. |
| «Toolstrip.DisableHighDpiImprovements» | «true»&#124;«false» | Указывает, является ли <xref:System.Windows.Forms.ToolStrip> элемент управления использует преимущества масштабирования и разметки улучшений, появившихся в .NET Framework 4.7. «true», чтобы отказаться от поддержки определения DPI; «false» в противном случае. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Настраивает Поддержка новых функций приложения Windows Forms. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> "Примечания"

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework. 

`<System.Windows.Forms.ApplicationConfigurationSection>` Элемент можно добавить один или несколько дочерних `<add>` элементов, каждый из которых определяет конкретный параметр конфигурации.  

Обзор поддержка высокого DPI в Windows Forms, см. в разделе [поддержка высокого DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Приложения Windows Forms, выполняемых в версиях Windows, начиная с Windows 10 Creators Edition и предназначенные для версий платформы .NET Framework, начиная с .NET Framework 4.7 можно настроить таким образом, чтобы воспользоваться преимуществами высокого уровня DPI усовершенствования, появившиеся в .NET Framework 4.7. Сюда входит следующее.

- Поддержка динамических сценариев точек на ДЮЙМ, в которых пользователь изменяет идентификации точек на ДЮЙМ или масштаб после запуска приложения Windows Forms.

- Усовершенствования в масштабировании и макет ряд Windows Forms элементы управления, такие как <xref:System.Windows.Forms.MonthCalendar> управления и <xref:System.Windows.Forms.CheckedListBox> элемента управления. 

Высокий уровень поддержки определения DPI является дополнительной функции; по умолчанию значение `DpiAwareness` является `false`. Вы можете выбрать поддержка Windows Forms для поддержки определения DPI, задав значение для раздела значение `PerMonitorV2` в файле конфигурации приложения. Если включена поддержка DPI, также включены все функции отдельных точек на ДЮЙМ. Сюда входит следующее.

- Сообщения, которые управляются изменения DPI `DisableDpiChangedMessageHandling` ключ.

- Динамические поддержка DPI, которая управляется `EnableWindowsFormsHighDpiAutoResizing` ключ.

- Один проход масштабирование элемента управления, который управляется `Form.DisableSinglePassControlScaling` для отдельных <xref:System.Windows.Forms.Form> управляет, путем `AnchorLayout.DisableSinglePassControlScaling` ключа для привязанные элементы управления, а также по `MonthCalendar.DisableSinglePassControlScaling` ключа для <xref:System.Windows.Forms.MonthCalendar> элемента управления 

- Высокий DPI масштабирования и разметки улучшений, которые управляются `CheckListBox.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.CheckedListBox> управления по `DataGridView.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.DataGridView> элемента управления и с помощью `Toolstrip.DisableHighDpiImprovements` ключа для <xref:System.Windows.Forms.ToolStrip> элемента управления.  

Один параметр по умолчанию согласиться, предоставляемые параметр `DpiAwareness` для `PerMonitorV2` подходит для новых приложений Windows Forms. Тем не менее можно затем отказаться отдельных высокий DPI улучшения, добавив соответствующий ключ в файле конфигурации приложения. Например чтобы воспользоваться преимуществами всех новых точек на ДЮЙМ функции предварительной за исключением поддержки динамического точек на ДЮЙМ, необходимо добавить следующее в файл конфигурации приложения:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
Как правило можно отказаться от определенный компонент так, как вы решили программным образом обрабатывать его.

Дополнительные сведения о благодаря преимуществам поддержка высокого DPI в приложениях Windows Forms, см. в разделе [поддержка высокого DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

Начиная с .NET Framework 4.7, элементы управления Windows Forms к возникновению ряда событий, связанные с изменением в масштабе DPI. К ним относятся <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, и <xref:System.Windows.Forms.Form.DpiChanged> события. Значение `DisableDpiChangedMessageHandling` определяет ключ ли эти события создаются в приложении Windows Forms. 

### <a name="single-pass-scaling"></a>Один проход масштабирование

Одной или несколькими pass Масштабирование влияет воспринимаемая пользователем скорость реагирования пользовательского интерфейса и внешний вид элементов пользовательского интерфейса, как они масштабируются. Начиная с .NET Framework 4.7, Windows Forms используется масштабирование один проход. В предыдущих версиях .NET Framework масштабирование было выполнено через несколько проходов, которые вызвала некоторые элементы управления масштабировать больше, чем была необходима. Масштабирование однократного прохода следует отключать только если приложение зависит от старого поведения.  

## <a name="see-also"></a>См. также
 
[Раздел конфигурации Windows Forms](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Поддержка высокого DPI в Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
