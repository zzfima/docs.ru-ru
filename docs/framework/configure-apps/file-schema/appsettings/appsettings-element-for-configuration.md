---
title: "&lt;appSettings&gt; элемент для &lt;конфигурации&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cebb9ba7ebeb483233276324289a4ddc5a0bc381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="appsettings-element-for-configuration"></a>\<appSettings > элемент для \<конфигурации >

Содержит пользовательские параметры приложения. Это предопределенный раздел параметров конфигурации в .NET Framework.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<appSettings >**

## <a name="syntax"></a>Синтаксис

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>Атрибут

|           | Описание: |
| --------- | ----------- |
| **file**  | Необязательный атрибут.<br><br>Указывает относительный путь к внешнему файлу, содержащему пользовательские параметры конфигурации приложения. Указанный файл содержит одинаковые параметры, заданные в  **\<Добавить >**,  **\<удалить >**, и  **\<снимите >** элементы и использует ту же пару ключ значение формата как эти элементы.<br><br>Указанный путь задается относительно основной файл конфигурации. Для приложения Windows Forms, это двоичный папку (например, */bin/debug*), не расположение файла конфигурации приложения. Для приложений Web Forms путь задается относительно корневой каталог приложения, где *web.config* находится файл.<br><br>Обратите внимание, что среда выполнения не учитывает атрибут, если не удается найти указанный файл. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание: |
| --- | ----------- |
| [**\<Конфигурация >** элемент](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание: |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | Добавляет пользовательский параметр приложения. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | Удаляет все ранее определенные параметры приложения. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | Удаляет ранее определенный параметр приложения. |

## <a name="remarks"></a>Примечания

 **\<AppSettings >** элемент хранит пользовательские данные конфигурации приложения, например строки подключения базы данных, пути к файлам, URL-адреса XML-веб-службы или любые другие пользовательские сведения о конфигурации приложение. Пары ключ значение, указанное в  **\<appSettings >** доступ к элементу в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.

Можно использовать **файл** атрибута в  **\<appSettings >** элемент *Web.config* и файлов конфигурации приложения. Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяет параметры, указанные в  **\<appSettings >** элемента. **Файл** атрибут может использоваться в исходном сценариях разработки группы управления, например, если пользователю необходимо переопределить параметры проекта, указанный в файле конфигурации приложения.

Файлы конфигурации, указанные по **файл** атрибут должен иметь корневой узел  **\<appSettings >** вместо  **\<конфигурации >**.

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

Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.

## <a name="see-also"></a>См. также

[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
