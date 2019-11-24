---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451326"
---
# <a name="gclohthreshold-element"></a>GCLOHThreshold element

Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>Синтаксис

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br />Specifies the threshold size that causes objects to go on the large object heap.|

### <a name="enabled-attribute"></a>enabled attribute

|значения|Описание|
|-----------|-----------------|
|`nnnn`|The threshold size, in bytes, that causes objects to go on the large object heap.|

## <a name="child-elements"></a>Дочерние элементы

Отсутствует.

## <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Заметки

This setting was introduced in .NET Framework 4.8.

## <a name="see-also"></a>См. также

- [Run-time settings schema](index.md)
- [Схема файла конфигурации](../index.md)
- [Основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md)
- [NET Core run-time config options for GC](../../../../core/run-time-config/garbage-collector.md)
