---
title: "Схема параметров приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "параметры приложения, схема [Windows Forms]"
  - "схема конфигурации [платформа .NET Framework], параметры приложения"
  - "параметры приложения схемы"
  - "Windows Forms, схема параметров приложения"
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: 3
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 3
---
# Схема параметров приложения
Параметры приложений позволяют приложению Windows Forms или ASP.NET сохранять и вызывать параметры области определения приложения и параметры области пользователя.  "Параметр" в данном контексте – это любая информация, относящаяся к приложению или к текущему пользователю, от строки подключения к базе данных до размера окна, предпочитаемого пользователем.  
  
 По умолчанию параметры приложения в приложении Windows Forms используют класс <xref:System.Configuration.LocalFileSettingsProvider>, использующий систему конфигурации .NET для хранения параметров в XML\-файлах конфигурации.  Дополнительные сведения о файлах, используемых параметрами приложения, см. в разделе [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md).  
  
 Параметры приложения определяют следующие элементы как часть файлов конфигурации.  
  
|Элемент|Описание|  
|-------------|--------------|  
|Элемент `<applicationSettings>`|Содержит все теги `<setting>`, относящиеся к приложению.|  
|Элемент `<userSettings>`|Содержит все теги `<setting>`, относящиеся к текущему пользователю.|  
|Элемент `<setting>`|Определяет параметр.  Является дочерним для элемента `<applicationSettings>` или `<userSettings>`.|  
|Элемент `<value>`|Определяет значение параметра.  Является дочерним для элемента `<setting>`.|  
  
## Элемент \<applicationSettings\>  
 Этот элемент содержит все теги \<setting\>, относящиеся к экземпляру приложения на клиентском компьютере.  Не содержит атрибуты.  
  
## Элемент \<userSettings\>  
 Этот элемент содержит все теги \<setting\>, относящиеся к пользователю, работающему с приложением.  Не содержит атрибуты.  
  
## Элемент \<setting\>  
 Этот элемент определяет параметр.  Он имеет следующие атрибуты.  
  
|Элемент|Описание|  
|-------------|--------------|  
|`name`|Обязательный.  Уникальный идентификатор параметра.  Параметры, созданные Visual Studio, сохраняются с именем `ProjectName``.Properties.Settings`.|  
|`serializedAs`|Обязательный.  Формат, используемый для сериализации в текстовое представление.  Допустимые значения:<br /><br /> -   `string`.  Значение сериализуется в виде строки с помощью класса <xref:System.ComponentModel.TypeConverter>.<br />-   `xml`.  Значение сериализуется с использованием сериализации XML.<br />-   `binary`.  Значение сериализуется с использованием двоичной сериализации.<br />-   `custom`.  Поставщик параметров имеет встроенные сведения об этом параметре для проведения сериализации и десериализации.<br />-   При использовании двоичной и пользовательской сериализации необходимо определить собственный класс параметров и использовать класс <xref:System.Configuration.SettingsSerializeAsAttribute> для задания двоичной или пользовательской сериализации.|  
  
## Элемент \<value\>  
 Этот элемент содержит значение параметра.  
  
## Пример  
 В следующем примере кода показан файл параметров приложения, определяющий два параметра области определения приложения и два параметра области пользователя.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </sectionGroup>  
        <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" >  
            <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />  
        </sectionGroup>  
    </configSections>  
    <applicationSettings>  
        <WindowsApplication1.Properties.Settings>  
            <setting name="Cursor" serializeAs="String">  
                <value>Default</value>  
            </setting>  
            <setting name="DoubleBuffering" serializeAs="String">  
                <value>False</value>  
            </setting>  
        </WindowsApplication1.Properties.Settings>  
    </applicationSettings>  
    <userSettings>  
        <WindowsApplication1.Properties.Settings>  
            <setting name="FormTitle" serializeAs="String">  
                <value>Form1</value>  
            </setting>  
            <setting name="FormSize" serializeAs="String">  
                <value>595, 536</value>  
            </setting>  
        </WindowsApplication1.Properties.Settings>  
    </userSettings>  
</configuration>  
```  
  
## См. также  
 [Общие сведения о параметрах приложений](../../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)