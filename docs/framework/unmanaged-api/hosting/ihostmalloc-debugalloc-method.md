---
title: Метод IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178036"
---
# <a name="ihostmallocdebugalloc-method"></a>Метод IHostMAlloc::DebugAlloc
Просит хост выделить указанное количество памяти из кучи и дополнительно отслеживать, где была выделена память.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbSize`  
 (в) Размер в байтах текущего запроса распределения памяти.  
  
 `dwCriticalLevel`  
 (в) Одно из значений [EMemoryCriticalLevel,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) указывающее на последствия сбоя выделения.  
  
 `pszFileName`  
 (в) Кодовый файл отладки выполнения.  
  
 `iLineNo`  
 (в) Номер строки, в `pszFileName` котором было запрошено распределение.  
  
 `ppMem`  
 (ваут) Указатель на выделенную память или null, если запрос не может быть завершен.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти было доступно для завершения запроса на выделение.|  
  
## <a name="remarks"></a>Remarks  
 CLR получает указатель интерфейса на экземпляр [IHostMalloc,](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) позвонив в [iHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) метод. `DebugAlloc`позволяет времени выполнения получать информацию о файле кода для использования во время отладки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Интерфейс IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
