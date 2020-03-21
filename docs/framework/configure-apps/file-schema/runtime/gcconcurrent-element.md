---
title: gcConcurrent Элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400983"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent> элемент

Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.

[\<конфигурация>](../configuration-element.md)\
&nbsp;&nbsp;[\<>выполнения](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a>Синтаксис

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|attribute|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br />Указывает, выполняет ли среда выполнения сборку мусора параллельно.|

#### <a name="enabled-attribute"></a>включенный атрибут

|Значение|Описание|
|-----------|-----------------|
|`false`|Не работает сбор мусора одновременно.|
|`true`|Сборка мусора выполняется параллельно. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

До .NET Framework 4 сбор мусора на рабочих станциях поддерживал параллельный сбор мусора, который выполнял сбор мусора в фоновом режиме на отдельном потоке. В .NET Framework 4 параллельный сбор мусора был заменен на фоновый GC, который также выполняет сбор мусора в фоновом режиме на отдельном потоке. Начиная с .NET Framework 4.5, сбор фоновых данных стал доступен в сборе мусора сервера. Элемент **gcConcurrent** контролирует, выполняет ли время выполнения либо одновременный, либо фоновый сбор мусора, если он доступен, или же он выполняет сбор мусора на переднем плане.

### <a name="to-disable-background-garbage-collection"></a>Чтобы отключить сбор фонового мусора

> [!WARNING]
> Начиная с .NET Framework 4, параллельный сбор мусора заменяется сбором фонового мусора. Термины *одновременно* и *фон* используются взаимозаменяемо в документации .NET Framework. Чтобы отключить сбор фонового мусора, используйте элемент **gcConcurrent,** как это обсуждается в этой статье.

По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам. Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора. При установке `enabled` атрибута **элемента gcConcurrent,** `false`время выполнения использует непараллельный сбор мусора, который оптимизируется для пропускной необходимости.

Следующий файл конфигурации отравливает сбор фонового мусора:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

Если в файле конфигурации машины есть параметр **gcConcurrentSetting,** он определяет значение по умолчанию для всех приложений .NET Framework. Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.

Для получения дополнительной информации о параллельном [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)и фоновом [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)сборе мусора [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) см. [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)

## <a name="example"></a>Пример

Следующий пример позволяет собирать фоновый мусор:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [Основные сведения о сборке мусора](../../../../standard/garbage-collection/fundamentals.md)
