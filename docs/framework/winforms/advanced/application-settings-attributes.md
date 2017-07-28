---
title: "Application Settings Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "application settings [Windows Forms], attributes"
  - "attributes [Windows Forms], application settings"
  - "wrapper classes, application settings"
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Application Settings Attributes
Архитектура параметров приложения обеспечивает целый ряд атрибутов, которые могут быть применены к классу\-оболочке параметров приложения или к отдельным свойствам этого класса.  Данные атрибуты проверяются во время выполнения инфраструктурой параметров приложения \(обычно поставщиком параметров\), чтобы настроить работу приложения в соответствии с указанными потребностям пользовательской программы\-оболочки.  
  
 Ниже перечислены атрибуты, которые могут быть применены к классу\-оболочке параметров приложения, к отдельным свойствам этого класса или и к классу, и к свойствам.  По определению, к каждому свойству параметров должен быть применен только один атрибут области определения — **UserScopedSettingAttribute** или **ApplicationScopedSettingAttribute**.  
  
> [!NOTE]
>  Для распознавания трех атрибутов, перечисленных далее, требуется только пользовательский поставщик параметров, производный от класса <xref:System.Configuration.SettingsProvider>: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute** и **DefaultSettingValueAttribute**.  
  
|Атрибут|Целевой объект|Описание|  
|-------------|--------------------|--------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Оба|Указывает короткое имя поставщика параметров, используемого для сохранения.<br /><br /> Если этот атрибут не задан, используется поставщик по умолчанию — <xref:System.Configuration.LocalFileSettingsProvider>.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Оба|Определяет свойство как параметр с областью определения пользователя.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Оба|Определяет свойство как параметр с областью определения приложения.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Свойство.|Указывает строку, которая может быть десериализована поставщиком в жестко заданное значение по умолчанию для этого свойства.<br /><br /> Для поставщика <xref:System.Configuration.LocalFileSettingsProvider> этот атрибут не требуется; поставщик переопределит любое значение, возвращаемое этим атрибутом, при наличии уже сохраненного значения.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Свойство.|Предоставляет описательные тесты для отдельных параметров, в основном используется средствами времени выполнения и разработки.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Класс|Содержит явное имя группы параметров.  Если этот атрибут отсутствует, класс <xref:System.Configuration.ApplicationSettingsBase> использует имя класса\-оболочки.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Класс|Предоставляет описательный тест для группы параметров, в основном используется средствами времени выполнения и разработки.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Оба|Указывает ноль или более служб управляемости, которые должны предоставляться группе параметров или свойству.  Доступные службы описаны перечислением <xref:System.Configuration.SettingsManageability>.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Свойство.|Показывает, что параметр принадлежит к особой предопределенной категории, такой как строка подключения, и, в силу этого, должен обрабатываться поставщиком параметров особым образом.  Предопределенные категории для этого атрибута определены перечислением <xref:System.Configuration.SpecialSetting>.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Оба|Задает предпочтительный механизм сериализации для группы параметров или свойства.  Доступные механизмы сериализации определены перечислением <xref:System.Configuration.SettingsSerializeAs>.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Свойство.|Указывает, что поставщик параметров должен отключить всю функциональность обновления приложения для помеченного свойства.|  
  
 *Класс* указывает, что атрибут может быть применен только к классу\-оболочке параметров приложения.  *Свойство* указывает, что атрибут может быть применен только к свойствам параметров.  *Класс и его свойства* указывает, что атрибут может применяться на обоих уровнях.  
  
## См. также  
 <xref:System.Configuration.ApplicationSettingsBase>   
 <xref:System.Configuration.SettingsProvider>   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)   
 [How to: Create Application Settings](http://msdn.microsoft.com/ru-ru/53b3af80-1c02-4e35-99c6-787663148945)