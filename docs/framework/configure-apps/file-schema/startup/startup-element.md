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
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699416"
---
# <a name="startup-element"></a>Элемент > запуска \<

Задает сведения о запуске среды CLR.

[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<запуска >**  

## <a name="syntax"></a>Синтаксис

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Указывает, следует ли включить политику активации среды выполнения .NET Framework 2,0 или использовать политику активации .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>атрибут useLegacyV2RuntimeActivationPolicy

|Значение|Описание|
|-----------|-----------------|
|`true`|Включите политику активации среды выполнения .NET Framework 2,0 для выбранной среды выполнения, чтобы привязать устаревшие методы активации среды выполнения (например, [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) к среде выполнения, выбранной из файла конфигурации, вместо того, чтобы заключать их в CLR версии 2,0. Таким же, если в файле конфигурации выбрана среда CLR версии 4 или более поздней, сборки в смешанном режиме, созданные в более ранних версиях .NET Framework, загружаются с выбранной версией среды CLR. Установка этого значения предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент.|
|`false`|Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, которая позволяет использовать устаревшие методы активации среды выполнения для загрузки среды CLR версии 1,1 или 2,0 в процесс. Установка этого значения предотвращает загрузку сборок в смешанном режиме в .NET Framework 4 или более поздней версии, если они не были созданы с помощью .NET Framework 4 или более поздней версии. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, созданные с помощью среды выполнения версии 1,1 или более поздней, должны использовать элемент **\<supportedRuntime >** .|
|[\<supportedRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|

## <a name="remarks"></a>Примечания

 **\<SupportedRuntime>** элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения. Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать элемент **\<requiredRuntime >** .

 Код запуска приложения, размещенного в Microsoft Internet Explorer, игнорирует элемент **> запуска\<** и его дочерние элементы.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy

 Этот атрибут полезен, если ваше приложение использует пути активации прежних версий, например [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и вы хотите, чтобы эти пути активировали версию 4 среды CLR вместо более ранней версии или если приложение создано с .NET Framework 4, но зависит от сборки в смешанном режиме, построенной с использованием более ранней версии .NET Framework. В этих сценариях присвойте атрибуту значение `true`.

> [!NOTE]
> Присвоение атрибуту значения `true` предотвращает загрузку CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент (см. раздел [параллельное выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Пример

 В следующем примере показано, как указать версию среды выполнения в файле конфигурации.

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

## <a name="see-also"></a>См. также:

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Как настроить приложение для поддержки .NET Framework 4 или более поздних версий](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Параллельное выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Внутрипроцессное параллельное выполнение](../../../deployment/in-process-side-by-side-execution.md)
