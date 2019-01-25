---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568157"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
[Поддерживается в .NET Framework 4.6 и более поздних версиях]  
  
 Возвращает перечислитель для всех методов, которые определены в указанный модуль NGen и в строке данного метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `inlinersModuleId`  
 [in] Идентификатор модуля NGen.  
  
 `inlineeModuleId`  
 [in] Идентификатор модуля, который определяет `inlineeMethodId`. Дополнительные сведения см. в разделе "Примечания".  
  
 `inlineeMethodId`  
 [in] Идентификатор метода как встроенный. Дополнительные сведения см. в разделе "Примечания".  
  
 `incompleteData`  
 [out] Флаг, указывающий, является ли `ppEnum` содержит все методы встраивания определенного метода.  Дополнительные сведения см. в разделе "Примечания".  
  
 `ppEnum`  
 [out] Указатель на адрес перечислителя  
  
## <a name="remarks"></a>Примечания  
 `inlineeModuleId` и `inlineeMethodId` вместе образуют полный идентификатор для метода, который может быть встроен. Предположим, например, модуль `A` определяет метод `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 и модуль Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Позволяет также предполагается, что `Fancy.AddTwice` inlines вызов к `SimpleAdd`. Профилировщик может использовать этот перечислитель для поиска, все методы, определенные в модуле B, какие встроенные `Simple.Add`, и результат будет перечислять `AddTwice`.  `inlineeModuleId` Идентификатор модуля `A`, и `inlineeeMethodId` идентификатор `Simple.Add(int a, int b)`.  
  
 Если `incompleteData` имеет значение true, после функции Возвращает перечислитель не содержит все методы встраивания определенного метода. Это может произойти, если в одном или более прямой или косвенной зависимости модуля inliners еще не были загружены. Если профилировщик должен точные данные, его следует повторить позднее при загрузке дополнительных модулей, предпочтительно при каждой загрузке модуля.  
  
 `EnumNgenModuleMethodsInliningThisMethod` Метод может использоваться для обхода ограничений на встраивание для ReJIT. ReJIT позволяет профилировщику измените реализацию метода и затем создать новый код для него в режиме реального времени. Например, мы изменим `Simple.Add` следующим образом:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Однако поскольку `Fancy.AddTwice` имеет уже встроена `Simple.Add`, он продолжает ведут себя так же как и раньше. Чтобы обойти это ограничение, вызывающий оператор имеет для поиска всех методов во всех модулях это в процессе настройки `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` на каждом из этих методов. Если методы, повторная компиляция, они будут иметь новое поведение `Simple.Add` вместо старого поведения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
