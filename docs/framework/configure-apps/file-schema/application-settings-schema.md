---
title: Схема параметров приложения
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f11be59941759687806591feb1edcce28b2119e6
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844238"
---
# <a name="application-settings-schema"></a>Схема параметров приложения

Параметры приложений позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры области приложения и уровня пользователя. В этом контексте *параметр* является любая информация, не относящиеся к приложению или к текущему пользователю — от строку подключения базы данных для пользователя предпочтительный размер окна по умолчанию.

По умолчанию использует параметры приложения в приложении Windows Forms <xref:System.Configuration.LocalFileSettingsProvider> класс, который использует систему конфигурации .NET для хранения параметров в файле конфигурации XML. Дополнительные сведения о файлах, используемых параметрами приложения, см. в разделе [архитектура параметров приложения](~/docs/framework/winforms/advanced/application-settings-architecture.md).

Параметры приложения определяет следующие элементы как часть файлов конфигурации, используемые в нем.

| Элемент                    | Описание:                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings >** | Содержит все  **\<параметр >** теги, относящиеся к приложению.                         |
| **\<userSettings >**        | Содержит все  **\<параметр >** теги, относящиеся к текущему пользователю.                        |
| **\<параметр >**             | Определяет параметр. Дочерним для элемента  **\<applicationSettings >** или  **\<userSettings >**. |
| **\<value>**               | Определяет значение параметра. Потомком  **\<параметр >**.                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > элемент

Этот элемент содержит все  **\<параметр >** теги, относящиеся к экземпляру приложения на клиентском компьютере. Атрибуты не определяются.

## <a name="usersettings-element"></a>\<userSettings > элемент

Этот элемент содержит все  **\<параметр >** теги, характерные для пользователя, который в настоящее время использует приложение. Атрибуты не определяются.

## <a name="setting-element"></a>\<Установка > элемент

Этот элемент определяет параметр. Он имеет следующие атрибуты.

| Атрибут        | Описание: |
| ---------------- | ----------- |
| **name**         | Обязательно. Уникальный идентификатор параметра. Параметры, созданные с помощью Visual Studio сохраняются с именем `ProjectName.Properties.Settings`. |
| **serializedAs** | Обязательно. Формат, используемый для сериализации значение к тексту. Допустимые значения:<br><br>- `string`. Значение сериализуется как строки с помощью <xref:System.ComponentModel.TypeConverter>.<br>- `xml`. Значение сериализуется с помощью XML-сериализации.<br>- `binary`. Значение сериализуется как двоичные кодировке текста, с использованием двоичной сериализации.<br />- `custom`. Поставщик параметров имеет распознает этот параметр и сериализует и десериализует его. |

## <a name="value-element"></a>\<Значение > элемент

Этот элемент содержит значение параметра.

## <a name="example"></a>Пример

В примере показан файл параметров приложения, который определяет два параметры приложения и двух параметров пользователя:

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
