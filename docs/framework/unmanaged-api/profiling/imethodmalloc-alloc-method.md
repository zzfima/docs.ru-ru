---
title: Метод IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54c38f9a9abc9a02ba4d84c9a41b2ef6b1f7cb69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528567"
---
# <a name="imethodmallocalloc-method"></a>Метод IMethodMalloc::Alloc
Пытается выделить указанный объем памяти для нового тела функции промежуточного языка MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cb`  
 [in] Число байтов, выделенных для тела метода.  
  
## <a name="remarks"></a>Примечания  
 Выделенная память начинается по адресу больше, чем базовый адрес модуля, связанного с данным распределителем. Другими словами каждый распределитель создается для определенного модуля и предпринимает попытку выделения памяти с положительным смещением от базового адреса. Если `Alloc` не удается выделить запрошенное число байт по адресу больше, чем базовый адрес модуля, он возвращает значение E_OUTOFMEMORY, независимо от фактического объема доступной памяти.  
  
 `Alloc` Метод должен использоваться в сочетании с [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** WindSee [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
