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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921250"
---
# <a name="configuration-element"></a>\<Элемент Configuration >

Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.

**\<configuration>**

## <a name="syntax"></a>Синтаксис

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

Отсутствуют

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<assemblyBinding >** ](assemblybinding-element-for-configuration.md) | Определяет политику привязки сборок на уровне конфигурации.|
| [Схема параметров > запуска  **\<** ](./startup/index.md) | Все элементы в схеме параметров запуска. |
| [Схема параметров **> среды выполнения \<** ](./runtime/index.md) | Все элементы в схеме параметров среды выполнения. |
| [Схема параметров **> System. Runtime. Remoting \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | Все элементы в схеме параметров удаленного взаимодействия. |
| [Схема параметров **System > .NET \<** ](./network/index.md) | Все элементы в схеме параметров сети. |
| [Схема параметров > криптографисеттингс  **\<** ](./cryptography/index.md) | Все элементы в схеме параметров шифрования. |
| [Схема разделов > конфигурации  **\<** ](configuration-sections-schema.md) | Все элементы в схеме параметров раздела конфигурации. |
| [Схема параметров трассировки и отладки](./trace-debug/index.md) | Все элементы в схеме параметров трассировки и отладки. |
| [Схема параметров конфигурации ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | Все элементы в схеме конфигурации ASP.NET, включая элементы для настройки веб-сайтов и приложений ASP.NET. Используется в файлах *Web. config* . |
| [Схема параметров > WebService  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | Все элементы в схеме параметров веб-служб. |
| [Схема веб-параметров](./web/index.md) | Все элементы схемы веб-параметров, в том числе элементы настройки способов работы ASP.NET с ведущими приложениями, такими как службы IIS. Используется в файлах *ASPNET. config* . |

## <a name="remarks"></a>Примечания

Каждый файл конфигурации должен содержать ровно один  **\<элемент конфигурации >** .

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
