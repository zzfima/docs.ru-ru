---
title: Метод IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>Метод IHostMemoryManager::VirtualAlloc
Служит в качестве логической программой-оболочкой для соответствующей функции Win32. Реализация Win32 `VirtualAlloc` резервирует или фиксирует диапазон страниц в виртуальном адресном пространстве вызывающего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pAddress`  
 [in] Указатель на начальный адрес области, чтобы выделить.  
  
 `dwSize`  
 [in] Размер в байтах, области.  
  
 `flAllocationType`  
 [in] Тип выделения памяти.  
  
 `flProtect`  
 [in] Защита памяти для области страницы должен быть выделен.  
  
 `dwCriticalLevel`  
 [in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) значение, указывающее влияние ошибки выделения.  
  
 `ppMem`  
 [out] Указатель на начальный адрес памяти или значение null, если запрос не может быть удовлетворен.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Не хватает памяти была доступна для выполнения запроса на выделение|  
  
## <a name="remarks"></a>Примечания  
 Для резервирования области в адресном пространстве процесса путем вызова `VirtualAlloc`. `pAddress` Параметр содержит начальный адрес блока памяти, требуется. Этот параметр обычно устанавливается в значение null. Операционная система хранит запись о диапазонах свободных адресов, доступных для процесса. Объект `pAddress` значение null предписывает системе резервирования размера. Кроме того можно предоставить определенный адрес, начиная для блока памяти. В обоих случаях выходной параметр `ppMem` возвращается как указатель на выделенную память. Сама функция возвращает значение HRESULT.  
  
 Win32 `VirtualAlloc` функция не имеет `ppMem` параметра и вместо этого возвращает указатель на выделенную память. Дополнительные сведения см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
