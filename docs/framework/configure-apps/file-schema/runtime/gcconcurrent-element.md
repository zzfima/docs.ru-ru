---
title: Элемент <gcConcurrent>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674598"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent > элемент

Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.

\<Конфигурация > \
\<Среда выполнения > \
\<gcConcurrent>

## <a name="syntax"></a>Синтаксис

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, выполняет ли среда выполнения сборку мусора параллельно.|

## <a name="enabled-attribute"></a>атрибут Enabled

|Значение|Описание:|
|-----------|-----------------|
|`false`|Не выполнять сборку мусора параллельно.|
|`true`|Сборка мусора выполняется параллельно. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание:|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Примечания

До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполнялась в фоновом режиме в отдельном потоке. В .NET Framework 4 параллельная сборка мусора была заменена фоновой сборкой мусора, которая также выполняется в фоновом режиме в отдельном потоке. Начиная с .NET Framework 4.5 фоновая сборка мусора стала доступна для сборки мусора сервера. `<gcConcurrent>` Элемент управляет, выполняет ли среда выполнения параллельную или фоновую сборку мусора, если таковой имеется, или он выполняет сборку мусора на переднем плане.

### <a name="to-disable-background-garbage-collection"></a>Чтобы отключить фоновую сборку мусора

> [!WARNING]
> Начиная с .NET Framework 4, параллельная сборка мусора заменена на фоновую сборку мусора. Условия *параллельных* и *фона* являются взаимозаменяемыми в документации по .NET Framework. Чтобы отключить фоновую сборку мусора, используйте элемент `<gcConcurrent>`, как описано в этом разделе.

По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам. Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора. Если атрибут `enabled` элемента `<gcConcurrent>` имеет значение `false`, среда выполнения использует непараллельную сборку мусора, которая оптимизирована по производительности. В следующем файле конфигурации отключается фоновая сборка мусора.

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 Если имеется `<gcConcurrentSetting>` параметр в файле конфигурации компьютера, он определяет значение по умолчанию для всех приложений .NET Framework. Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.

 Дополнительные сведения о параллельной и фоновой сборки мусора, см. в разделе [параллельная сборка мусора](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) статьи [основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md) статьи.

## <a name="example"></a>Пример

В следующем примере включается параллельная сборка мусора:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md)
