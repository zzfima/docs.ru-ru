---
title: "Метод ICorProfilerInfo2::GetFunctionInfo2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b0c288b88c868bc6e324ec57b3956344f03f34e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a>Метод ICorProfilerInfo2::GetFunctionInfo2
Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `funcId`  
 [входной] Идентификатор функции, для которой нужно получить родительский класс и другую информацию.  
  
 `frameInfo`  
 [входной] Значение `COR_PRF_FRAME_INFO`, указывающее на информацию о кадре стека.  
  
 `pClassId`  
 [выходной] Указатель на родительский класс функции.  
  
 `pModuleId`  
 [выходной] Указатель на модуль, в котором определен родительский класс функции.  
  
 `pToken`  
 [выходной] Указатель на токен метаданных функции.  
  
 `cTypeArgs`  
 [in] Размер массива `typeArgs`.  
  
 `pcTypeArgs`  
 [выходной] Указатель на общее количество значений `ClassID`.  
  
 `typeArgs`  
 [выходной] Массив значений `ClassID`, каждое из которых является идентификатором аргумента типа функции. При возврате из метода в параметре `typeArgs` содержатся все или некоторые значения `ClassID`.  
  
## <a name="remarks"></a>Примечания  
 Профилировщик кода может вызвать [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) для получения [метаданные](../../../../docs/framework/unmanaged-api/metadata/index.md) интерфейс для данного модуля. Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.  
  
 Идентификатор класса и аргументы типа, возвращенные с помощью параметров `pClassId` и `typeArgs`, зависят от значения, переданного в параметре `frameInfo`, как показано в таблице ниже.  
  
|Значение параметра `frameInfo`|Результат|  
|----------------------------------------|------------|  
|Значение `COR_PRF_FRAME_INFO`, полученное в результате обратного вызова `FunctionEnter2`|Значение `ClassID`, возвращенное в расположении, на которое ссылается параметр `pClassId`, и все аргументы типа, возвращенные в массиве `typeArgs`, будут точными.|  
|Объект `COR_PRF_FRAME_INFO`, полученный из источника, отличного от обратного вызова `FunctionEnter2`|Точное значение `ClassID` и аргументы типа определить нельзя. То есть, `ClassID` может иметь значение NULL, а некоторые аргументы типа могут быть возвращены в виде объекта <xref:System.Object>.|  
|Нуль|Точное значение `ClassID` и аргументы типа определить нельзя. То есть, `ClassID` может иметь значение NULL, а некоторые аргументы типа могут быть возвращены в виде объекта <xref:System.Object>.|  
  
 После возврата из метода `GetFunctionInfo2` нужно убедиться в том, что буфер `typeArgs` был достаточно велик, чтобы вместить в себя все значения `ClassID`. Для этого сравните значение, на которое указывает параметр `pcTypeArgs`, со значением параметра `cTypeArgs`. Если параметр `pcTypeArgs` указывает на значение, превышающее значение `cTypeArgs`, деленное на размер значения `ClassID`, нужно выделить буфер `pcTypeArgs` большего размера, обновить параметр `cTypeArgs`, задав новый, больший размер и вызвать метод `GetFunctionInfo2` снова.  
  
 Кроме того, сначала можно вызвать метод `GetFunctionInfo2` с буфером `pcTypeArgs` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcTypeArgs`, деленному на размер значения `ClassID`, и вызвать метод `GetFunctionInfo2` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
