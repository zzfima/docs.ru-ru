---
title: "Атрибуты параметров приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2ed0a0393f505d0126508e574b1cd9abe138866
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="application-settings-attributes"></a>Атрибуты параметров приложения
Архитектура параметров приложения предоставляет множество атрибутов, которые могут быть применены к классу-оболочке параметров приложения или его отдельных свойств. Эти атрибуты проверяются во время выполнения инфраструктурой параметров приложения, часто поставщиком параметров, чтобы адаптировать работу с указанными потребностям пользовательской оболочки.  
  
 В следующей таблице перечислены атрибуты, которые могут быть применены к классу-оболочке параметров приложения и отдельные свойства этого класса. По определению только одну область атрибут —**UserScopedSettingAttribute** или **ApplicationScopedSettingAttribute**— должен быть применен к каждой свойства параметров.  
  
> [!NOTE]
>  Настраиваемый поставщик параметров, производный от <xref:System.Configuration.SettingsProvider> класса, необходимо только, чтобы распознать следующие три атрибута: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, и **DefaultSettingValueAttribute**.  
  
|Атрибут|целевого объекта|Описание:|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Оба значения|Указывает короткое имя поставщика параметров, используемого для сохранения.<br /><br /> Если этот атрибут не задан, поставщик по умолчанию <xref:System.Configuration.LocalFileSettingsProvider>, подразумевается.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Оба значения|Определяет свойство как параметр области пользователя приложения.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Оба значения|Определяет свойство как параметр приложения для приложения.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Свойство.|Задает строку, которая может быть десериализована поставщиком в жестко по умолчанию для этого свойства.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> Этот атрибут не требуется и переопределяет любое значение, если этот атрибут при наличии значение уже сохранен.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Свойство.|Предоставляет описательные тесты для отдельных параметров, в основном используется средствами во время выполнения и во время разработки.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Класс|Содержит явное имя группы параметров. Если этот атрибут отсутствует, <xref:System.Configuration.ApplicationSettingsBase> использует имя класса-оболочки.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Класс|Предоставляет описательный тест для группы параметров, в основном используется средствами во время выполнения и во время разработки.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Оба значения|Указывает ноль или более служб управляемости, которые должны передаваться в группы параметров или свойства. Описываются доступные службы <xref:System.Configuration.SettingsManageability> перечисления.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Свойство.|Указывает, что параметр принадлежит к особой предопределенной категории, такие как строка подключения, который предлагает специальную обработку поставщика параметров. Стандартные категории для этого атрибута определяется <xref:System.Configuration.SpecialSetting> перечисления.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Оба значения|Задает предпочтительный механизм сериализации для группы параметров или свойства. Доступные механизмы сериализации определяются <xref:System.Configuration.SettingsSerializeAs> перечисления.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Свойство.|Указывает, что поставщик параметров должен отключить всю функциональность обновления приложения для помеченного свойства.|  
  
 *Класс* указывает, что атрибут может применяться только к классу-оболочке параметров приложения. *Свойство* указывает, что атрибут может быть применен только к свойствам параметров. *Оба* указывает, что атрибут может применяться на обоих уровнях.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Архитектура параметров приложения](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Практическое руководство. Создание параметров приложения](http://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
