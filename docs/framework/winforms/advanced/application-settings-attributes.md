---
title: Атрибуты параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: 9ed549cb1e10b22c4fa34d984133a6be11dfab44
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481166"
---
# <a name="application-settings-attributes"></a>Атрибуты параметров приложения
Архитектура параметров приложения предоставляет множество атрибутов, которые могут быть применены к классу-оболочке параметров приложения или его отдельным свойствам. Эти атрибуты проверяются во время выполнения с помощью инфраструктуры параметры приложения, часто поставщиком параметров, чтобы адаптировать работу с указанными потребностям настраиваемой оболочки.  
  
 В следующей таблице перечислены атрибуты, которые могут применяться к классу-оболочке параметров приложения и отдельные свойства этого класса. По определению, только одну область атрибут —**UserScopedSettingAttribute** или **ApplicationScopedSettingAttribute**— должны применяться для каждого свойства параметров.  
  
> [!NOTE]
>  Настраиваемый поставщик параметров, производный от <xref:System.Configuration.SettingsProvider> класса, требуется только для распознавания следующие три атрибута: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, и **DefaultSettingValueAttribute**.  
  
|Атрибут|целевого объекта|Описание|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Оба значения|Задает короткое имя поставщика параметров, используемый для сохранения состояния.<br /><br /> Если этот атрибут не задан, поставщик по умолчанию, <xref:System.Configuration.LocalFileSettingsProvider>, предполагается, что.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Оба значения|Определяет свойство как параметр приложений пользователя.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Оба значения|Определяет свойство как параметр приложения.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Свойство.|Указывает строку, которая может быть десериализован поставщиком жестко заданную по умолчанию для этого свойства.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> Этот атрибут не требуется и переопределяет любое значение, предоставляемые этим атрибутом Если значение уже сохранены.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Свойство.|Предоставляет описательный тест для отдельных параметров, в основном используется средствами времени выполнения и во время разработки.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Класс|Содержит явное имя для группы параметров. Если этот атрибут отсутствует, <xref:System.Configuration.ApplicationSettingsBase> использует имя класса-оболочки.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Класс|Предоставляет описательный тест для группы параметров, в основном используется средствами времени выполнения и во время разработки.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Оба значения|Указывает ноль или более служб управляемости, которые должна быть представлена группа параметров или свойство. Описываются доступные службы <xref:System.Configuration.SettingsManageability> перечисления.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Свойство.|Указывает, что параметр принадлежит к особой предопределенной категории, например строку подключения, предлагаемое специальной обработки поставщика параметров. Стандартные категории для этого атрибута определяется <xref:System.Configuration.SpecialSetting> перечисления.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Оба значения|Указывает предпочтительный механизм сериализации для группы параметров или свойства. Доступные механизмы сериализации определяются <xref:System.Configuration.SettingsSerializeAs> перечисления.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Свойство.|Указывает, что поставщик параметров должен отключить всю функциональность обновления приложения для помеченного свойства.|  
  
 *Класс* указывает, что атрибут может применяться только к классу-оболочке параметров приложения. *Свойство* указывает, что атрибут может быть применен только к свойствам параметров. *Оба* указывает, что атрибут может применяться на любом уровне.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Архитектура параметров приложения](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Практическое руководство. Создание параметров приложения](https://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
