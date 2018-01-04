---
title: "Метод ICorProfilerInfo::BeginInprocDebugging"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.BeginInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91306bbea7b099f7e9e408f8bf69625f1d7da68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>Метод ICorProfilerInfo::BeginInprocDebugging
Инициализирует внутрипроцессную поддержку отладки. Этот метод является устаревшим в .NET Framework версии 2.0.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fThisThreadOnly`  
 [in] Это значение равно `true` инициализировать поддержку отладки для текущего потока; задайте для него значение `false` инициализировать поддержку отладки для всех потоков.  
  
 `pdwProfilerContext`  
 [out] Указатель на возвращаемое значение, идентифицирующее сеанс отладки.  
  
## <a name="remarks"></a>Примечания  
 Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1. Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки. Однако из-за отзывов клиентов внутрипроцессная отладка удалено из платформы .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия платформы .NET framework:** 1.0  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
