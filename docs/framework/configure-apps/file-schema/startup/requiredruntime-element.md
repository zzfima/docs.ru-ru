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
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697487"
---
# <a name="requiredruntime-element"></a>\<requiredRuntime > элемент

Указывает, что приложение поддерживает только версию 1.0 среды CLR. Этот элемент является устаревшим и больше не должен использоваться. Вместо этого следует использовать элемент [`supportedRuntime`](supportedruntime-element.md) .

[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<запуска >** ](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<requiredRuntime >**  

## <a name="syntax"></a>Синтаксис

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`version`|Необязательный атрибут.<br /><br /> Строковое значение, указывающее версию .NET Framework, которую поддерживает это приложение. Строковое значение должно соответствовать имени каталога, обнаруженному в корне установки .NET Framework. Содержимое строкового значения не анализируется.|
|`safemode`|Необязательный атрибут.<br /><br /> Указывает, будет ли код запуска среды выполнения выполнять поиск в реестре для определения версии среды выполнения.|

## <a name="safemode-attribute"></a>атрибут безопасный режим

|Значение|Описание|
|-----------|-----------------|
|`false`|Код запуска среды выполнения выполняет поиск в реестре. Это значение по умолчанию.|
|`true`|Код запуска среды выполнения не выполняет поиск в реестре.|

### <a name="child-elements"></a>Дочерние элементы

Нет

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`startup`|Содержит элемент `<requiredRuntime>`.|

## <a name="remarks"></a>Примечания
 Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать элемент `<requiredRuntime>`. Приложения, созданные с помощью версии 1,1 или более поздней версии среды выполнения, должны использовать элемент `<supportedRuntime>`.

> [!NOTE]
> При использовании функции [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать элемент `<requiredRuntime>` для всех версий среды выполнения. Элемент `<supportedRuntime>` игнорируется при использовании [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 Строка атрибута `version` должна соответствовать имени папки установки для указанной версии .NET Framework. Эта строка не интерпретируется. Если код запуска среды выполнения не находит совпадающую папку, среда выполнения не загружается; код запуска отображает сообщение об ошибке и завершает работу.

> [!NOTE]
> Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует элемент `<requiredRuntime>`.

## <a name="example"></a>Пример

В следующем примере показано, как указать версию среды выполнения в файле конфигурации.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>См. также:

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Как настроить приложение для поддержки .NET Framework 4 или более поздних версий](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
