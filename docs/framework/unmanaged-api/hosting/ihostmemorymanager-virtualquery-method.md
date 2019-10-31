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
ms.openlocfilehash: 00ec0b92a9f7151ee9b831c85548c4f61d87af68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192036"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>Метод IHostMemoryManager::VirtualQuery
Служит логической оболочкой для соответствующей функции Win32. Реализация `VirtualQuery` Win32 извлекает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `lpAddress`  
 окне Указатель на адрес в виртуальной памяти для запроса.  
  
 `lpBuffer`  
 заполняет Указатель на структуру, содержащую сведения о заданной области памяти.  
  
 `dwLength`  
 окне Размер (в байтах) буфера, на который `lpBuffer` указывает.  
  
 `pResult`  
 заполняет Указатель на число байтов, возвращенных информационным буфером.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 `VirtualQuery` предоставляет сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса. Эта реализация задает для параметра `pResult` значение, равное числу байтов, возвращаемых в информационном буфере, и возвращает значение HRESULT. В функции `VirtualQuery` Win32 возвращаемое значение является размером буфера. Дополнительные сведения см. в документации по платформе Windows.  
  
> [!IMPORTANT]
> Реализация `VirtualQuery` в операционной системе не вызывает взаимоблокировки и может выполняться до завершения с помощью случайных потоков, приостановленных в пользовательском коде. При реализации размещенной версии этого метода следует соблюдать осторожность.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
