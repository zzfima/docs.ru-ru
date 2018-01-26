---
title: "Метод ICorProfilerInfo::GetILFunctionBody"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 035c2a1926d80b4aaea57523b4ecdd3da6873efe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>Метод ICorProfilerInfo::GetILFunctionBody
Возвращает указатель на основной части метода в код MSIL (MSIL), начиная с его заголовка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, в которой находится функция.  
  
 `methodId`  
 [in] Токен метаданных для метода.  
  
 `ppMethodHeader`  
 [out] Указатель на метод заголовок.  
  
 `pcbMethodSize`  
 [out] Целое число, указывающее размер метода.  
  
## <a name="remarks"></a>Примечания  
 Метод действует в модуле, в которой они находятся. Поскольку `GetILFunctionBody` метод предназначен для предоставления доступа в MSIL-код, прежде чем он будет загружен с общеязыковой среды выполнения (CLR), он использует токен метаданных метода для поиска к нужному экземпляру.  
  
 `GetILFunctionBody`Можно также вернуть CORPROF_E_FUNCTION_NOT_IL HRESULT Если `methodId` указывает на метод без любой MSIL кода (таких как абстрактный метод или для платформы, вызовите метод (PInvoke)).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
