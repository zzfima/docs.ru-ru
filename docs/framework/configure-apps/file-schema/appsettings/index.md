---
title: Схема параметров приложения
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215431"
---
# <a name="app-settings-schema"></a>Схема параметров приложения

Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)

| Элемент | Описание |
| ------- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Содержит теги **\<add>** , **\<clear>** и **\<remove>** , управляющие параметрами приложения. Имеет необязательный атрибут **file**. |
| [ **\<add>** ](add-element-for-appsettings.md) | Определяет параметр. Дочерний элемент **\<appSettings>** . Обязательные атрибуты — **key** и **value**. |
| [ **\<clear>** ](clear-element-for-appsettings.md) | Удаляет все параметры. Дочерний элемент **\<appSettings>** . Не имеет атрибутов. |
| [ **\<remove>** ](remove-element-for-appsettings.md) | Удаляет параметр. Дочерний элемент **\<appSettings>** . Требуется атрибут **key**. |

## <a name="appsettings-element"></a>Элемент \<appSettings>

Этот элемент содержит теги **\<add>** , **\<clear>** и **\<remove>** , управляющие параметрами приложения. Определяет необязательный атрибут для **file**.

## <a name="add-element"></a>Элемент \<add>

Добавляет пользовательский параметр приложения в виде пары "имя-значение" в коллекцию параметров приложения. Определяет атрибуты для **key** и **value**.

## <a name="clear-element"></a>Элемент \<clear>

Удаляет все ссылки на унаследованные пользовательские параметры приложения, разрешая только ссылки, добавленные с помощью элементов **\<add>** после элемента **\<clear>** . Атрибуты не определяются.

## <a name="remove-element"></a>Элемент \<remove>

Удаляет ссылку на унаследованный пользовательский параметр приложения из коллекции параметров приложения. Определяет атрибут для **key**.

## <a name="example"></a>Пример

В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a>См. также:

- [Общие сведения о параметрах приложений](../../../winforms/advanced/application-settings-overview.md)
- [Архитектура параметров приложения](../../../winforms/advanced/application-settings-architecture.md)
