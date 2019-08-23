---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56b23b6d5fca6d0527d509c9b6a6fc6dd82336
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920786"
---
# <a name="gccpugroup-element"></a>\<Элемент > Гккпуграуп

Определяет, поддерживает ли сборка мусора несколько групп ЦП.

\<> конфигурации \
\<> среды выполнения \
\<Гккпуграуп >

## <a name="syntax"></a>Синтаксис

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, поддерживает ли сборка мусора несколько групп ЦП.|

## <a name="enabled-attribute"></a>Атрибут enabled

|Значение|Описание|
|-----------|-----------------|
|`false`|Сборка мусора не поддерживает несколько групп ЦП. Это значение по умолчанию.|
|`true`|Сборка мусора поддерживает несколько групп ЦП, если включена сборка мусора сервера.|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Примечания

Если на компьютере установлено несколько групп ЦП и включена сборка мусора сервера (см [ \<. элемент > gcServer](gcserver-element.md) ), включение этого элемента расширяет сбор мусора во всех группах ЦП и учитывает все ядра при создании и сбалансированные кучи.

> [!NOTE]
> Этот элемент применяется только к потокам сборки мусора. Чтобы среда выполнения распространяла пользовательские потоки во всех группах ЦП, необходимо также включить [ \<элемент > Thread_UseAllCpuGroups](thread-useallcpugroups-element.md) .

## <a name="example"></a>Пример

В следующем примере показано, как включить сбор мусора для нескольких групп ЦП.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Отключение параллельной сборки мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Сборка мусора рабочей станции и сборка мусора сервера](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
