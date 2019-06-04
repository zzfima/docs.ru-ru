---
title: Элемент <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e40ca31ddc40cccbeb3b8dda1d148ddec5032d7c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489550"
---
# <a name="startup-element"></a>\<Startup > элемент

Указывает информация запуска среды CLR.

 \<Конфигурация > \<startup >

## <a name="syntax"></a>Синтаксис

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Указывает, следует ли включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения или использовать политику активации .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>атрибут useLegacyV2RuntimeActivationPolicy

|Значение|Описание|
|-----------|-----------------|
|`true`|Включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения для выбранной среды выполнения, используемого для привязки методы активации старой среды выполнения (таких как [функция CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) в среду выполнения, выбранный из файла конфигурации вместо ограничивая их в среде CLR версии 2.0. Таким образом Если вы выбрали CLR версии 4 или более поздней версии из файла конфигурации, смешанных сборок, созданных в более ранних версиях платформы .NET Framework, загружаются с выбранной версией среды CLR. Установка этого значения предотвращает CLR версии 1.1 или среду CLR версии 2.0 загрузку в одном процессе, эффективно отключение функции-process side-by-side.|
|`false`|Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, чтобы разрешить старой среды выполнения методов активации для загрузки в процесс среды CLR версии 1.1 или 2.0. Установка этого значения предотвращает смешанной сборки от загрузки в .NET Framework 4 или более поздней версии, если они были созданы с помощью .NET Framework 4 или более поздней версии. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, созданные с помощью среды выполнения версии 1.1 или более поздней, должны использовать  **\<supportedRuntime >** элемент.|
|[\<supportedRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|

## <a name="remarks"></a>Примечания

 **\<SupportedRuntime>** элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения. Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать  **\<requiredRuntime >** элемент.

 Код запуска для приложения, размещенного в Internet Explorer не учитывает  **\<startup >** элемент и его дочерние элементы.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy

 Этот атрибут полезен, если приложение использует устаревшие активации пути, такие как [функция CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и нужно, чтобы эти пути для активации версии 4 среды CLR вместо более ранней версии, или если приложение созданные с помощью .NET Framework 4, но имеет зависимость от сборки смешанного режима, созданных с помощью более ранней версии платформы .NET Framework. В этих сценариях, задать для атрибута `true`.

> [!NOTE]
> Присвоение атрибуту `true` предотвращает загрузку в одном процессе, эффективно отключение функции-process side-by-side CLR версии 1.1 или среду CLR версии 2.0 (см. в разделе [Side-by-Side выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Пример

 Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Выполнение Side-by-Side COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Внутрипроцессное параллельное выполнение](../../../deployment/in-process-side-by-side-execution.md)
