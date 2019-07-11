---
title: Метод IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a60d954cf4331d46a4667afba1e9dee0d214f0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767679"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>Метод IHostMemoryManager::VirtualFree
Служит в качестве логической программой-оболочкой для соответствующей функции Win32. Реализация Win32 `VirtualFree` освобождает, разблокирует или освобождает и разблокирует диапазон страниц в пространстве виртуальных адресов вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `lpAddress`  
 [in] Указатель на базовый адрес страниц виртуальной памяти, который требуется освободить.  
  
 `dwSize`  
 [in] Размер в байтах, области, который требуется освободить.  
  
 `dwFreeType`  
 [in] Тип операции освобождения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`VirtualFree` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION|Для освобождения памяти, который не был выделен через узел была предпринята.|  
  
## <a name="remarks"></a>Примечания  
 `VirtualFree` Освобождает страницы виртуальной памяти, связанные с `lpAddress` параметры с помощью предыдущего вызова [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) функции. Пытается освободить память, выделенную через узел не должен возвращать значение HOST_E_INVALIDOPERATION.  
  
 Семантика идентична семантике реализация Win32 `VirtualFree`. Дополнительные сведения см. в документации платформы Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Интерфейс IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
