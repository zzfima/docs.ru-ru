---
title: "Схема параметров приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: "3"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d93a18b17e0d6b8e413903fb84dc6b427d94f6af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="application-settings-schema"></a>Схема параметров приложения

Параметры приложений позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры области приложения и пользователя. В этом контексте *параметр* является любая информация, которая конкретного приложения или только к текущему пользователю, что-либо из строки подключения к базе данных пользователю предпочитаемые размер окна по умолчанию.

По умолчанию параметры приложения в приложении Windows Forms использует <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в файл конфигурации XML. Дополнительные сведения о файлах, используемых параметрами приложения см. в разделе [архитектура параметров приложения](~/docs/framework/winforms/advanced/application-settings-architecture.md).

Параметры приложения определяют следующие элементы как часть файлов конфигурации, используемые в нем.

| Элемент                    | Описание                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings >** | Содержит все  **\<параметр >** теги, относящиеся к приложению.                         |
| **\<userSettings >**        | Содержит все  **\<параметр >** теги, относящиеся к текущему пользователю.                        |
| **\<параметр >**             | Определяет параметр. Дочерним для элемента  **\<applicationSettings >** или  **\<userSettings >**. |
| **\<value>**               | Определяет значение параметра. Дочерний  **\<параметр >**.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > элемент

Этот элемент содержит все  **\<параметр >** теги, относящиеся к экземпляру приложения на клиентском компьютере. Атрибуты не определяются.

## <a name="usersettings-element"></a>\<userSettings > элемент

Этот элемент содержит все  **\<параметр >** теги, относящиеся к пользователю, работающему с приложением. Атрибуты не определяются.

## <a name="setting-element"></a>\<Настройка > элемент

Этот элемент определяет параметр. Он имеет следующие атрибуты.

| Атрибут        | Описание |
| ---------------- | ----------- |
| **name**         | Обязательный. Уникальный идентификатор параметра. Параметры, созданные с помощью Visual Studio сохраняются с именем `ProjectName.Properties.Settings`. |
| **serializedAs** | Обязательный. Формат, используемый для сериализации значения в текст. Допустимые значения:<br><br>- `string`. Значение сериализуется как строки с помощью <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Значение сериализуется с использованием XML-сериализации.<br>- `binary`. Значение сериализуется как текст в кодировке двоичного файла с использованием двоичной сериализации.<br />- `custom`. Поставщик параметров имеет встроенные сведения об этот параметр и сериализует и десериализует его. |

## <a name="value-element"></a>\<Значение > элемент

Этот элемент содержит значение параметра.

## <a name="example"></a>Пример

Следующий пример показывает файл параметров приложения, который определяет два параметры приложения и двух параметров пользователя:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
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

## <a name="see-also"></a>См. также

[Общие сведения о параметрах приложений](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[Архитектура параметров приложения](~/docs/framework/winforms/advanced/application-settings-architecture.md)
