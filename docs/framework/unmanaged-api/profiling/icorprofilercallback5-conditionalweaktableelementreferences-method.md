---
title: Метод ICorProfilerCallback5::ConditionalWeakTableElementReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39ce72451f3a375f0cd3adb67a431162fc421a93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041606"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>Метод ICorProfilerCallback5::ConditionalWeakTableElementReferences

Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a>Параметры

`cRootRefs`\
[в] Количество элементов в массивах `keyRefIds`, `valueRefIds` и `rootIds`.

`keyRefIds`\
[в] Массив идентификаторов объектов, каждый из которых содержит `ObjectID` для основного элемента в зависимости пары дескриптора.

`valueRefIds`\
[в] Массив идентификаторов объектов, каждый из которых содержит `ObjectID` для дополнительного элемента в зависимости пары дескриптора. (`keyRefIds[i]` отслеживает `valueRefIds[i]` проверки активности.)

`rootIds`\
[в] Массив значений `GCHandleID`, указывающий на целое число, который содержит дополнительные сведения о корне сборки мусора.

Ни одно из значений `ObjectID`, возвращаемых методом `ConditionalWeakTableElementReferences` во время обратного вызова самого себя, не является допустимым, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `ConditionalWeakTableElementReferences`. Вызов `GarbageCollectionFinished` означает, что все объекты перемещены в новые расположения и можно проводить проверку.

## <a name="example"></a>Пример

В следующем примере кода показано, как реализовать [ICorProfilerCallback5](icorprofilercallback5-interface.md) и использовать этот метод.

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a>Примечания

Профилировщик для [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] или более поздних версий реализует [ICorProfilerCallback5](icorprofilercallback5-interface.md) интерфейс и записывает зависимости, указанные по `ConditionalWeakTableElementReferences` метод. `ICorProfilerCallback5` предоставляет полный набор зависимостей между используемыми объектами, представленный `ConditionalWeakTable` записей. Эти зависимости и элемент поле ссылки, определяемое [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) позволяют управляемому профилировщику создавать полный граф используемых объектов.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** CorProf.idl, CorProf.h

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback5](icorprofilercallback5-interface.md)