---
title: Интерфейс IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077788"
---
# <a name="imethodmalloc-interface"></a>Интерфейс IMethodMalloc
Предоставляет метод для выделения памяти для нового тела функции промежуточного языка MSIL.  
  
> [!NOTE]
>  `IMethodMalloc` Интерфейс является простым средством выделения памяти. Можно выделить память, но не освободит его.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Пытается выделить указанный объем памяти для нового тела функции MSIL.|  
  
## <a name="remarks"></a>Примечания  
 Каждый распределитель конкретного модуля и гарантирует, что тело функции будет использовать с положительным смещением от базового модуля. Память сверх базового модуля может быть драгоценное, поэтому распределителя должен использоваться для выделения памяти только для тела функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
