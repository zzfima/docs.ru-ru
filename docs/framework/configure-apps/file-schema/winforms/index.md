---
title: Раздел конфигурации Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 4a54df0b6301f1aae14d5561c91c6792cb0a1620
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109813"
---
# <a name="windows-forms-configuration-section"></a>Раздел конфигурации Windows Forms
Параметры конфигурации Windows Forms позволяют приложению Windows Forms хранить и извлекать сведения о настроенных параметрах приложения, таких как поддержка нескольких мониторов, поддержка высокого разрешения (DPI) и другие предопределенные параметры конфигурации.

Параметры конфигурации приложения Windows Forms хранятся в элементе `System.Windows.Forms.ApplicationConfigurationSection` файла конфигурации приложения.

## <a name="syntax"></a>Синтаксис

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствует.

### <a name="child-elements"></a>Дочерние элементы

Элемент  |Описание |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | Добавляет ключ параметра конфигурации с указанным значением. |

### <a name="parent-elements"></a>Родительские элементы

Элемент  |Описание |
---------|---------|
[\<configuration>](../configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями Windows Forms. |

## <a name="remarks"></a>Заметки

Начиная с версии .NET Framework 4.7 элемент `<System.Windows.Forms.ApplicationConfigurationSection>` позволяет настраивать в приложениях Windows Forms функции, добавленные в последних выпусках .NET Framework. 

Элемент `<System.Windows.Forms.ApplicationConfigurationSection>` может содержать один или несколько дочерних элементов [`<add>`](windows-forms-add-configuration-element.md), каждый из которых определяет конкретный параметр конфигурации.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [Поддержка высокого DPI в Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
