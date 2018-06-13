---
title: Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459675"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
[Поддерживается в .NET Framework 4.6 и более поздних версиях]  
  
 Возвращает перечислитель для всех методов, определенных в указанный модуль NGen и встроенные данный метод.  
  
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
 [in] Идентификатор метода является встроенной. Дополнительные сведения см. в разделе "Примечания".  
  
 `incompleteData`  
 [out] Флаг, указывающий, является ли `ppEnum` содержит все методы встраивания данный метод.  Дополнительные сведения см. в разделе "Примечания".  
  
 `ppEnum`  
 [out] Указатель на адрес объекта перечислителя  
  
## <a name="remarks"></a>Примечания  
 `inlineeModuleId` и `inlineeMethodId` вместе образуют полный идентификатор для метода, который может быть встроен. Например, предположим, модуль `A` определяет метод `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 и модуль Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Позволяет также предполагается, что `Fancy.AddTwice` внедряет вызов к `SimpleAdd`. Профилировщик может использовать этот перечислитель найти все методы, определенные в модуле B какие встроенного `Simple.Add`, и результат будет перечислять `AddTwice`.  `inlineeModuleId` Идентификатор модуля `A`, и `inlineeeMethodId` идентификатор `Simple.Add(int a, int b)`.  
  
 Если `incompleteData` имеет значение true, после функции Возвращает перечислитель не содержит все методы встраивания данный метод. Это может произойти, когда один или более прямых или косвенных зависимостей модуля inliners еще не были загружены. Если профилировщик должен точные данные, его следует повторить позднее при загрузке дополнительных модулей, лучше всего при каждой загрузке модуля.  
  
 `EnumNgenModuleMethodsInliningThisMethod` Метод можно использовать для обхода ограничений на встраивание для ReJIT. ReJIT позволяет профилировщику измените реализацию метода и затем создать новый код для него на ходу. Например, мы изменяем `Simple.Add` следующим образом:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Однако поскольку `Fancy.AddTwice` имеет уже встроена `Simple.Add`, он по-прежнему действуют так же как и раньше. Чтобы обойти это ограничение, вызывающий оператор имеет для поиска всех методов во всех модулях, встроенные `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` на каждом из этих методов. Если методы, повторная компиляция, они будут иметь новое поведение `Simple.Add` вместо старого поведения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
