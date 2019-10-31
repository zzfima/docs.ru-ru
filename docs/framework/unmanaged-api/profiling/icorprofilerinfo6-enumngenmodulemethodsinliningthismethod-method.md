---
title: Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130374"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod

Возвращает перечислитель для всех методов, определенных в заданном модуле NGen, и встроенный метод.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>Параметры

`inlinersModuleId`\
окне Идентификатор модуля NGen.

`inlineeModuleId`\
окне Идентификатор модуля, который определяет `inlineeMethodId`. Дополнительные сведения см. в разделе "Примечания".

`inlineeMethodId`\
окне Идентификатор встроенного метода. Дополнительные сведения см. в разделе "Примечания".

`incompleteData`\
заполняет Флаг, указывающий, содержит ли `ppEnum` все методы, выставляемые для данного метода.  Дополнительные сведения см. в разделе "Примечания".

`ppEnum`\
заполняет Указатель на адрес перечислителя

## <a name="remarks"></a>Заметки

`inlineeModuleId` и `inlineeMethodId` вместе формируют полный идентификатор метода, который может быть встроенным. Например, предположим, что модуль `A` определяет метод `Simple.Add`:

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

а модуль B определяет `Fancy.AddTwice`:

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Также предполагается, что `Fancy.AddTwice` выдает вызов `SimpleAdd`. Профилировщик может использовать этот перечислитель для поиска всех методов, определенных в модуле B, которые встроены `Simple.Add`, и результатом будет перечисление `AddTwice`.  `inlineeModuleId` — это идентификатор `A`модуля, а `inlineeMethodId` — идентификатор `Simple.Add(int a, int b)`.

Если `incompleteData` имеет значение true после возврата функции, перечислитель не содержит все методы, выставляемые в данный метод. Это может произойти, если одна или несколько непосредственных или косвенных зависимостей модуля "вкладыши" еще не загружены. Если профилировщику требуются точные данные, необходимо повторить попытку позже, когда загрузится больше модулей, лучше при каждой загрузке модуля.

Метод `EnumNgenModuleMethodsInliningThisMethod` можно использовать для обхода ограничений встраивания для ReJIT. ReJIT позволяет профилировщику изменить реализацию метода, а затем создать новый код для него в режиме реального времени. Например, можно изменить `Simple.Add` следующим образом:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Однако, поскольку `Fancy.AddTwice` уже встроены `Simple.Add`, она по-разному работает так же, как и раньше. Чтобы обойти это ограничение, вызывающий объект должен найти все методы во всех модулях, которые встроены `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` в каждом из этих методов. При повторной компиляции методов они будут иметь новое поведение `Simple.Add`, а не старое поведение.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo6](icorprofilerinfo6-interface.md)
