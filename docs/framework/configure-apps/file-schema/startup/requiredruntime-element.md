---
title: Элемент <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 5e528a8b81fa3d9abc4f345d18f01e33f483a4a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673846"
---
# <a name="requiredruntime-element"></a>\<requiredRuntime > элемент

Указывает, что приложение поддерживает только версию 1.0 среды CLR. Этот элемент устарел и больше не используется. [ `supportedRuntime` ](supportedruntime-element.md) Элемента, которые должны использоваться вместо нее.

\<Конфигурация > \<startup > \<requiredRuntime >

## <a name="syntax"></a>Синтаксис

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`version`|Необязательный атрибут.<br /><br /> Строковое значение, указывающее версию платформы .NET Framework, которая поддерживается данным приложением. Строковое значение должно соответствовать имени каталога, найден в корневом каталоге установки .NET Framework. Содержимое строкового значения не анализируется.|
|`safemode`|Необязательный атрибут.<br /><br /> Указывает, выполняет ли код запуска среды выполнения реестра для определения версии среды выполнения.|

## <a name="safemode-attribute"></a>атрибут безопасный режим

|Значение|Описание|
|-----------|-----------------|
|`false`|Код запуска среды выполнения ищет в реестре. Это значение по умолчанию.|
|`true`|Код запуска среды выполнения не выглядит в реестре.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`startup`|Содержит `<requiredRuntime>` элемент.|

## <a name="remarks"></a>Примечания
 Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент. Приложения, созданные с помощью версии 1.1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.

> [!NOTE]
> Если вы используете [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) функции для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения. `<supportedRuntime>` Элемент учитывается при использовании [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 `version` Строки атрибута должно соответствовать имени папки установки для указанной версии платформы .NET Framework. Эта строка не интерпретируется. Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска, отобразится сообщение об ошибке и завершает работу.

> [!NOTE]
> Код запуска для приложения, размещенного в Microsoft Internet Explorer не учитывает `<requiredRuntime>` элемент.

## <a name="example"></a>Пример

Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)