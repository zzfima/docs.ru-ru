---
title: <startup> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153739"
---
# <a name="startup-element"></a>\<элемент запуска>

Определяет информацию о запуске запуска общего языка.

[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;**\<>стартапа**  

## <a name="syntax"></a>Синтаксис

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|attribute|Описание|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Уточняется, включать ли политику активации времени выполнения .NET Framework 2.0 или использовать политику активации .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy атрибут

|Значение|Описание|
|-----------|-----------------|
|`true`|Включить политику активации времени выполнения .NET 2.0 для выбранного времени выполнения, которая заключается в том, чтобы связать устаревшие методы активации времени выполнения (например, [функцию CorBindToRuntimeEx)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)с выбранным из файла конфигурации вместо того, чтобы укупорывать их в версию CLR 2.0. Таким образом, если версия CLR 4 или более позднее выбрана из файла конфигурации, сборки смешанного режима, созданные с более ранними версиями рамочного .NET, загружаются с выбранной версией CLR. Установка этого значения предотвращает загрузку версии CLR 1.1 или CLR 2.0 в тот же процесс, что фактически отключит функцию «в процессе» бок о бок.|
|`false`|Используйте политику активации по умолчанию для системы .NET 4 и позже, которая должна позволить устаревшим методам активации времени выполнения загрузить версию CLR 1.1 или 2.0 в процесс. Установка этого значения предотвращает загрузку сборок смешанного режима в рамках .NET 4 или позже, если они не были построены с помощью .NET Framework 4 или позже. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<требуетсяRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. Приложения, построенные с версией времени выполнения 1.1 или позже, должны использовать ** \<поддерживаемыйэлемент>** элемент.|
|[\<поддерживаетRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|

## <a name="remarks"></a>Remarks

 ** \<Поддерживаемыйэлемент>** элемент должен использоваться всеми приложениями, построенными с использованием версии 1.1 или позже времени выполнения. Приложения, созданные для поддержки только версии 1.0 времени выполнения, должны использовать ** \<необходимый элементRuntime>.**

 Код запуска приложения, размещенного в Microsoft Internet Explorer, игнорирует ** \<запуск>** элементии и его элементы ребенка.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy

 Этот атрибут полезен, если приложение использует устаревшие пути активации, такие как [функция CorBindToRuntimeEx,](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)и вы хотите, чтобы эти пути активировали версию 4 CLR вместо более ранней версии, или если ваше приложение построено с помощью .NET Framework 4, но имеет зависимость от сборки смешанного режима, построенной с более ранней версией рамочного .NET. В этих сценариях установите атрибут. `true`

> [!NOTE]
> Установка атрибута `true` предотвращает загрузку версии CLR 1.1 или CLR 2.0 в тот же процесс, эффективно отключая функцию «в процессе» бок о бок (см. [бок о бок для COM Interop).](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))

## <a name="example"></a>Пример

 В следующем примере показано, как указать версию времени выполнения в файле конфигурации.

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

## <a name="see-also"></a>См. также раздел

- [Настройки стартапа Схема](index.md)
- [Схема конфигурации файлов](../index.md)
- [Как: Нанастройка приложения для поддержки .NET Framework 4 или более поздних версий](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Параллельное выполнение для COM- взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Внутрипроцессное параллельное выполнение](../../../deployment/in-process-side-by-side-execution.md)
