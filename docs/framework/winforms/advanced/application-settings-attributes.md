---
title: Атрибуты параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: b38ed931cab3a333a56dd027d5843b1c8f00dcb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916687"
---
# <a name="application-settings-attributes"></a>Атрибуты параметров приложения
Архитектура параметров приложения предоставляет множество атрибутов, которые можно применить к классу-оболочке параметров приложения или к его отдельным свойствам. Эти атрибуты изучаются во время выполнения инфраструктурой параметров приложения, часто в частности поставщику параметров, чтобы адаптировать свою работу к указанным потребностям пользовательской оболочки.  
  
 В следующей таблице перечислены атрибуты, которые могут быть применены к классу-оболочке параметров приложения, отдельным свойствам этого класса или обоим. По определению для каждого свойства параметров необходимо применять только один атрибут области (**UserScopedSettingAttribute** или **ApplicationScopedSettingAttribute**).  
  
> [!NOTE]
> Поставщик настраиваемых параметров, производный от <xref:System.Configuration.SettingsProvider> класса, должен распознать только следующие три атрибута: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**и **DefaultSettingValueAttribute**.  
  
|Атрибут|целевого объекта|Описание|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Оба|Указывает короткое имя поставщика параметров, которое будет использоваться для сохраняемости.<br /><br /> Если этот атрибут не указан, предполагается, что используется <xref:System.Configuration.LocalFileSettingsProvider>поставщик по умолчанию.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Оба|Определяет свойство как параметр приложения с областью действия пользователя.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Оба|Определяет свойство как параметр приложения в области приложения.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Свойство.|Указывает строку, которая может быть десериализована поставщиком в жестко заданное значение по умолчанию для этого свойства.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> Атрибут не требует этого атрибута и переопределяет любое значение, предоставленное этим атрибутом, если уже сохранено значение.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Свойство.|Предоставляет описательный тест для отдельного параметра, используемый главным образом средствами времени выполнения и времени разработки.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Класс|Предоставляет явное имя для группы параметров. Если этот атрибут отсутствует, <xref:System.Configuration.ApplicationSettingsBase> использует имя класса-оболочки.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Класс|Предоставляет описательный тест для группы параметров, который в основном используется средствами времени выполнения и времени разработки.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Оба|Указывает ноль или более служб управления, которые должны быть предоставлены группе параметров или свойству. Доступные службы описаны <xref:System.Configuration.SettingsManageability> перечислением.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Свойство.|Указывает, что параметр относится к специальной, предопределенной категории, такой как строка подключения, которая предлагает специальную обработку поставщиком параметров. Стандартные категории для этого атрибута определяются <xref:System.Configuration.SpecialSetting> перечислением.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Оба|Указывает предпочтительный механизм сериализации для группы параметров или свойства. Доступные механизмы сериализации определяются <xref:System.Configuration.SettingsSerializeAs> перечислением.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Свойство.|Указывает, что поставщик параметров должен отключить все функции обновления приложения для помеченного свойства.|  
  
 *Класс* указывает, что атрибут может применяться только к классу-оболочке параметров приложения. *Свойство* указывает, что атрибут может применяться только к свойствам параметров. *Оба* значения указывают, что атрибут можно применять на любом уровне.  
  
## <a name="see-also"></a>См. также

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Архитектура параметров приложения](application-settings-architecture.md)
- [Практическое руководство. Создание параметров приложения](how-to-create-application-settings.md)
