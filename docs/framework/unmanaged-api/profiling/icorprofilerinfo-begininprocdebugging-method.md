---
title: Метод ICorProfilerInfo::BeginInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864301"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>Метод ICorProfilerInfo::BeginInprocDebugging
Инициализирует поддержку внутрипроцессного отладки. Этот метод является устаревшим в .NET Framework версии 2,0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a>Параметры  
 `fThisThreadOnly`  
 окне Присвойте этому параметру значение `true`, чтобы инициализировать поддержку отладки только для текущего потока; Задайте для него значение `false`, чтобы инициализировать поддержку отладки для всех потоков.  
  
 `pdwProfilerContext`  
 заполняет Указатель на возвращаемое значение, идентифицирующее сеанс отладки.  
  
## <a name="remarks"></a>Заметки  
 Службы отладки CLR поддерживали ограниченную внутрипроцессную отладку в .NET Framework версиях 1,0 и 1,1. В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки. Однако из-за отзывов клиентов внутрипроцессный процесс отладки был удален из .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия .NET Framework:** 1,0  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
