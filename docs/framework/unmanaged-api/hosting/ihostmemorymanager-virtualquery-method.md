---
title: Метод IHostMemoryManager::VirtualQuery
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 885871f3e6b3f10bfb7d660e2d6889e243ef751b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734368"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>Метод IHostMemoryManager::VirtualQuery
Служит в качестве логической программой-оболочкой для соответствующей функции Win32. Реализация Win32 `VirtualQuery` извлекает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lpAddress`  
 [in] Указатель на адрес в виртуальной памяти, должны запрашиваться.  
  
 `lpBuffer`  
 [out] Указатель на структуру, содержащую сведения о регионе указанной области памяти.  
  
 `dwLength`  
 [in] Размер в байтах буфера, `lpBuffer` указывает.  
  
 `pResult`  
 [out] Указатель на число байтов, возвращенных в буфере сведения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `VirtualQuery` сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса. Эта реализация задает значение `pResult` параметр число байтов, возвращаемых в буфере сведения и возвращает значение HRESULT. В Win32 `VirtualQuery` функция, возвращаемое значение представляет размер буфера. Дополнительные сведения см. в документации платформы Windows.  
  
> [!IMPORTANT]
>  Реализация операционной системы `VirtualQuery` не приводит к взаимоблокировке и выполняются до завершения с помощью случайной приостановки потоков в пользовательском коде. Используйте особую осторожность при реализации размещенных версия этого метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
