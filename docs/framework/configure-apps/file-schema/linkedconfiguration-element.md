---
title: '&lt;linkedConfiguration&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 71769efa1233fc8a693219dc02ae56ea39c164e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743801"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > элемент

Указание файла конфигурации, который следует включить.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**

## <a name="syntax"></a>Синтаксис

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **href**  | Обязательный атрибут.<br><br>URL-адрес файла конфигурации для включения. Поддерживается только формат **href** атрибут `file://`. Поддерживаются локальные файлы и файлы UNC. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<assemblyBinding >** элемент](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Определяет политику привязки сборок на уровне конфигурации. |

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

**\<LinkedConfiguration >** элемент упрощает обслуживание для сборок компонентов. Если один или несколько приложений используют сборку, которая имеет файл конфигурации, находящихся в известное местоположение, можно использовать файлы конфигурации приложений, использующих сборку  **\<linkedConfiguration >** элемент для включения файла конфигурации сборки, вместо того чтобы включать сведения о конфигурации напрямую. При обслуживании сборки компонентов обновление общего файла конфигурации содержит обновленные сведения о конфигурации для всех приложений, использующих сборку.

> [!NOTE]
> **\<LinkedConfiguration >** элемент не поддерживается для приложений с Windows side-by-side манифесты.

Связанные файлы конфигурации действуют следующие правила:

- Параметры в файлах конфигурации, включенный только влияет на политику привязки загрузчика и используются только загрузчиком. Включенные файлы конфигурации могут иметь параметры, отличные от политики привязки, но эти параметры не оказывает никакого воздействия.

- Поддерживается только формат `href` атрибут `file://`. Поддерживаются локальные файлы и файлы UNC.

- Не имеет ограничений на количество связанных конфигураций для файла конфигурации.

- Все связанные файлы конфигурации объединяются в один файл, аналогично поведению объекта `#include` директив в C/C++.

- **\<LinkedConfiguration >** элемент допускается только в файлах конфигурации приложения; он игнорируется в *Machine.config*.

- Обнаружены циклические ссылки и удалены. То есть если  **\<linkedConfiguration >** элементов ряда файлов конфигурации образуют цикл, цикл обнаруживается остановлена.

## <a name="example"></a>Пример

В следующем примере показано, как можно включить файл конфигурации с локального жесткого диска:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>См. также

[**\<assemblyBinding >** элемент](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
