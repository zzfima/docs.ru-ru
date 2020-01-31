---
title: Метод ICorProfilerInfo2::GetClassIDInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 64d2cd76dafb1a51814b916b5ce73fb08cdcaef9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868864"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>Метод ICorProfilerInfo2::GetClassIDInfo2
Получает родительский модуль и маркер метаданных для открытого универсального определения указанного класса, `ClassID` его родительского класса и `ClassID` для каждого аргумента типа, если он имеется, класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса, для которого будут извлекаться сведения.  
  
 `pModuleId`  
 заполняет Указатель на идентификатор родительского модуля для открытого универсального определения указанного класса.  
  
 `pTypeDefToken`  
 заполняет Указатель на маркер метаданных для открытого универсального определения указанного класса.  
  
 `pParentClassId`  
 [out] Указатель на идентификатор родительского класса.  
  
 `cNumTypeArgs`  
 [in] Размер массива `typeArgs`.  
  
 `pcNumTypeArgs`  
 [out] Указатель на общее число доступных элементов.  
  
 `typeArgs`  
 [out] Массив значений `ClassID`, каждое из которых представляет идентификатор аргумента типа класса. При возврате метода в массиве `typeArgs` будут содержаться все или некоторые доступные значения `ClassID`.  
  
## <a name="remarks"></a>Заметки  
 Метод `GetClassIDInfo2` аналогичен методу [ICorProfilerInfo:: жетклассидинфо](icorprofilerinfo-getclassidinfo-method.md) , но `GetClassIDInfo2` получает дополнительные сведения о универсальном типе.  
  
 Чтобы получить интерфейс [метаданных](../../../../docs/framework/unmanaged-api/metadata/index.md) для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) . Токен метаданных, возвращенный в расположение, на которое ссылается `pTypeDefToken`, можно впоследствии использовать для доступа к метаданным класса.  
  
 После возврата метода `GetClassIDInfo2` необходимо убедиться, что буфер `typeArgs` был достаточно велик, чтобы вместить в себя все значения `ClassID`. Для этого сравните значение, на которое указывает параметр `pcNumTypeArgs`, со значением параметра `cNumTypeArgs`. Если параметр `pcNumTypeArgs` указывает на значение, превышающее значение `cNumTypeArgs`, выделите буфер `typeArgs` большего размера, обновите параметр `cNumTypeArgs`, задав новый, больший размер, и вызовите метод `GetClassIDInfo2` снова.  
  
 Кроме того, сначала можно вызвать метод `GetClassIDInfo2` с буфером `typeArgs` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера `typeArgs` равным значению, возвращенному в параметре `pcNumTypeArgs`, и вызвать метод `GetClassIDInfo2` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
