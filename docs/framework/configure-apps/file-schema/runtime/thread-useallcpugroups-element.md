---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115399"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups > элемент

Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**  

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

|значения|Описание|
|-----------|-----------------|
|`false`|Среда выполнения не распределяет управляемые потоки между несколькими группами ЦП. Это значение по умолчанию.|
|`true`|Среда выполнения распределяет управляемые потоки между несколькими группами ЦП, если компьютер имеет несколько групп ЦП, а элемент [\<гккпуграуп >](gccpugroup-element.md) включен.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Заметки

Если компьютер имеет несколько групп ЦП, включение этого элемента приводит к тому, что среда выполнения распределяет управляемые потоки по всем группам ЦП. Чтобы использовать эту функцию, необходимо также включить элемент [\<гккпуграуп >](gccpugroup-element.md) , который расширяет сбор мусора на все группы ЦП и учитывает все ядра при создании и балансировке куч. Чтобы включить элемент [\<гккпуграуп >](gccpugroup-element.md) , необходимо включить элемент [\<gcServer >](gcserver-element.md) . Если эти элементы не включены, включение элемента `<Thread_UseAllCpuGroups>` не оказывает никакого влияния.

## <a name="example"></a>Пример

В следующем примере показано, как включить поддержку нескольких групп ЦП.

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

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [\<Гккпуграуп > элемент](gccpugroup-element.md)
