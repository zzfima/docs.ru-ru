---
title: Указатель функции PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ee003d668916baec313c6115cc12826286f6cdd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>Указатель функции PFN_CLRDataCreateInstance
Указывает на функцию, которая создает объект интерфейса для заданного целевого элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор интерфейса для создания экземпляра.  
  
 `target`  
 [in] Указатель на реализации пользователя [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , представляющий целевой элемент, для которого необходимо создать объект интерфейса.  
  
 `iface`  
 [out] Указатель на адрес объекта, возвращенный интерфейс.  
  
## <a name="remarks"></a>Примечания  
 `ICLRDataTarget` Объект реализуется модулем записи отладчика. Реализация зависит от типа представляемого целевого элемента. Конечный элемент может быть процесс, дамп памяти, удаленный компьютер и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
