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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860986"
---
# <a name="imethodmalloc-interface"></a>Интерфейс IMethodMalloc
Предоставляет метод для выделения памяти для нового текста функции MSIL.  
  
> [!NOTE]
> Интерфейс `IMethodMalloc` — это простой механизм выделения памяти. Она позволяет выделить память, но не освобождает ее.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](imethodmalloc-alloc-method.md)|Пытается выделить указанный объем памяти для нового текста функции MSIL.|  
  
## <a name="remarks"></a>Заметки  
 Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля. Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы профилирования](profiling-interfaces.md)
