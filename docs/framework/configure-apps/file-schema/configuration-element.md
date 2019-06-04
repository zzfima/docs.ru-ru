---
title: Элемент <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705419"
---
# <a name="configuration-element"></a>\<Конфигурация > элемент

Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Синтаксис

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Атрибуты

Нет

## <a name="parent-element"></a>Родительский элемент

Нет

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<assemblyBinding >** ](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Определяет политику привязки сборок на уровне конфигурации.|
| [ **\<Startup >** параметры схемы](~/docs/framework/configure-apps/file-schema/startup/index.md) | Все элементы в схеме параметров запуска. |
| [ **\<Среда выполнения >** параметры схемы](~/docs/framework/configure-apps/file-schema/runtime/index.md) | Все элементы в схеме параметров среды выполнения. |
| [ **\<System.Runtime.Remoting >** параметры схемы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Все элементы в схеме параметров удаленного взаимодействия. |
| [ **\<system.Net >** параметры схемы](~/docs/framework/configure-apps/file-schema/network/index.md) | Все элементы в схеме параметров сети. |
| [ **\<cryptographySettings >** параметры схемы](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | Все элементы в схеме параметров криптографии. |
| [ **\<Конфигурация >** Схема разделов](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | Все элементы в схеме параметров раздела конфигурации. |
| [Схема параметров трассировки и отладки](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | Все элементы в схеме параметров трассировки и отладки. |
| [Схема параметров конфигурации ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Все элементы схемы конфигурации ASP.NET, в том числе элементы настройки веб-сайтов ASP.NET и приложений. Используется в *Web.config* файлов. |
| [ **\<веб-службы >** параметры схемы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Все элементы в схеме параметров веб-служб. |
| [Схема веб-параметров](~/docs/framework/configure-apps/file-schema/web/index.md) | Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS. Используется в *aspnet.config* файлов. |

## <a name="remarks"></a>Примечания

Каждый файл конфигурации должен содержать ровно один  **\<конфигурации >** элемент.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
