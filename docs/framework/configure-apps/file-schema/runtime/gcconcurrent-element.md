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
ms.openlocfilehash: 4897462e20b193496c44d26923d0d0e2a13f7dd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116814"
---
# <a name="gcconcurrent-element"></a>\<gcConcurrent > элемент

Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<gcConcurrent >**  

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

## <a name="enabled-attribute"></a>Включенный атрибут

|значения|Описание|
|-----------|-----------------|
|`false`|Не выполняется параллельное выполнение сборки мусора.|
|`true`|Сборка мусора выполняется параллельно. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Заметки

До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполнялась в фоновом режиме в отдельном потоке. В .NET Framework 4 параллельная сборка мусора была заменена фоновой сборкой мусора, которая также выполняется в фоновом режиме в отдельном потоке. Начиная с .NET Framework 4.5 фоновая сборка мусора стала доступна для сборки мусора сервера. Элемент `<gcConcurrent>` определяет, выполняет ли среда выполнения параллельную или фоновую сборку мусора, если она доступна, или же она выполняет сборку мусора на переднем плане.

### <a name="to-disable-background-garbage-collection"></a>Отключение фоновой сборки мусора

> [!WARNING]
> Начиная с .NET Framework 4, параллельная сборка мусора заменена на фоновую сборку мусора. *Одновременные* и *фоновые* термины в документации по .NET Framework используются взаимозаменяемыми. Чтобы отключить фоновую сборку мусора, используйте элемент `<gcConcurrent>`, как описано в этом разделе.

По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам. Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора. Если атрибут `enabled` элемента `<gcConcurrent>` имеет значение `false`, среда выполнения использует непараллельную сборку мусора, которая оптимизирована по производительности. В следующем файле конфигурации отключается фоновая сборка мусора.

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 Если в файле конфигурации компьютера имеется параметр `<gcConcurrentSetting>`, он определяет значение по умолчанию для всех .NET Framework приложений. Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.

 Дополнительные сведения о параллельной и фоновой сборке мусора см. в разделе [параллельная сборка мусора](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) статьи [основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md) .

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
