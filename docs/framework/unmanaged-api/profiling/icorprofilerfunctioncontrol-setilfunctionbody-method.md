---
title: "Метод ICorProfilerFunctionControl::SetILFunctionBody"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9469435186a5aef130ca4ebef27a4613afeb921c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>Метод ICorProfilerFunctionControl::SetILFunctionBody
Заменяет тело метода на языке CIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cbNewILMethodHeader`  
 [in] Общий размер нового кода CIL, включая заголовок и все структуры после тела.  
  
 `pbNewILMethodHeader`  
 [in] Указатель на новый заголовок на языке CIL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие специфичные результаты HRESULT.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Замена выполнена успешно.|  
  
## <a name="remarks"></a>Примечания  
 В отличие от [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метода `SetILFunctionBody` метод управляет памятью, требуемой для нового тела на языке CIL. Это означает, что предоставленное профилировщиком тело на языке CIL не имеет выделенной с помощью [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) интерфейс или в пределах определенного диапазона. Его можно разместить в любой куче. Профилировщик может освободить память, используемая для тела на языке CIL после `SetILFunctionBody` возвращает.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
