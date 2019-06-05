---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9758e009e012c8af5f5f7bd19dcd21f34b8c7d96
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689738"
---
# <a name="threaduseallcpugroups-element"></a>\<Thread_UseAllCpuGroups > элемент

Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.

\<Конфигурация > \
\<Среда выполнения > \
\<Thread_UseAllCpuGroups>

## <a name="syntax"></a>Синтаксис

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.|

## <a name="enabled-attribute"></a>Атрибут enabled

|Значение|Описание|
|-----------|-----------------|
|`false`|Среда выполнения не распространяет управляемые потоки по нескольким группам ЦП. Это значение по умолчанию.|
|`true`|Среда выполнения распространяет управляемые потоки по нескольким группам ЦП, если компьютер имеет несколько групп ЦП и [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) включен элемент.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Примечания

Если компьютер имеет несколько групп ЦП, позволяя причины этого элемента выполнение распределенного управляемые потоки во всех группах ЦП. Чтобы использовать эту функцию, необходимо также включить [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент, который учитывает все ядра во время создания и распределения куч и расширяет их возможности сбора мусора для всех групп ЦП. Включение [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент требует включения [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент. Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемент не оказывает влияния.

## <a name="example"></a>Пример

Приведенный ниже показано, как включить поддержку нескольких групп ЦП.

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<GCCpuGroup > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
