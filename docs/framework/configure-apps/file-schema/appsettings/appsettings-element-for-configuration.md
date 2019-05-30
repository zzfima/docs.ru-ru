---
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e8f85be2efe972fc45230855d18649a89f2fbd61
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300821"
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > элемент для \<configuration >

Содержит пользовательские параметры приложения. Это раздел стандартные конфигурации, предоставляемые платформой .NET Framework.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; **\<appSettings >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **file**  | Необязательный атрибут.<br><br>Указывает относительный путь во внешний файл, содержащий пользовательские параметры конфигурации приложения. Указанный файл содержит одинаковые параметры, заданные в **\<Добавить >** , **\<удалить >** , и **\<снимите >** элементы и использует формата одной пары ключ/значение, что и эти элементы.<br><br>Указанный путь задается относительно основной файл конфигурации. Для приложения Windows Forms, это двоичного папка (например, */bin/debug*), не расположение файла конфигурации приложения. Для приложений Web Forms, этот путь задается относительно корневого каталога приложения, где *web.config* он находится.<br><br>Обратите внимание на то, что среда выполнения игнорирует атрибут, если не удается найти указанный файл. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<Конфигурация >** элемент](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<add>** ](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Добавляет пользовательский параметр приложения. |
| [ **\<clear>** ](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Удаляет все ранее определенные параметры приложения. |
| [ **\<remove>** ](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Удаляет ранее определенный параметр приложения. |

## <a name="remarks"></a>Примечания

**\<AppSettings >** элемент сохраняет сведения о конфигурации пользовательского приложения, например строки подключения к базам данных, пути к файлам, URL-адреса XML-веб-служб или любые другие сведения о пользовательской конфигурации приложение. Пары ключ/значение, указанное в  **\<appSettings >** доступ к элементу в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.

Можно использовать **файл** атрибут в  **\<appSettings >** элемент *Web.config* и файлах конфигурации приложения. Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в  **\<appSettings >** элемент. **Файл** атрибут может использоваться в сценариев управления версиями team development, например когда пользователь хочет переопределить параметры проекта, указанный в файле конфигурации приложения.

Файлы конфигурации, заданные **файл** атрибут должен иметь корневой узел **\<appSettings >** вместо **\<конфигурации >** .

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

## <a name="configuration-file"></a>файл конфигурации

Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
