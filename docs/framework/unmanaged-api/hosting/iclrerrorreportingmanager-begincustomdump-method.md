---
title: Метод ICLRErrorReportingManager::BeginCustomDump
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5d58a90901b7d7cb80ea7f25401b857b4d4875e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434516"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>Метод ICLRErrorReportingManager::BeginCustomDump
Указывает конфигурацию пользовательских дампов кучи для отчета об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwFlavor`  
 [in] Объект [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) значение, указывающее тип дампа кучи, на которых можно создать дамп пользовательской кучи.  
  
 `dwNumItems`  
 [in] Длина `items` массива. Если `dwFlavor` не DUMP_FLAVOR_Mini, `dwNumItems` должно быть равно нулю.  
  
 `items`  
 [in] Массив [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) экземпляров, указав элементы для добавления мини-дампа. Если `dwFlavor` не DUMP_FLAVOR_Mini, `items` должен иметь значение null.  
  
 `dwReserved`  
 [in] Зарезервировано для будущего использования.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `BeginCustomDump` Метод задает конфигурацию пользовательского дампа кучи. [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) метод очищает конфигурацию пользовательского дампа кучи и освобождает все связанные состояния. Он должен вызываться после завершения пользовательской кучи дампа.  
  
> [!IMPORTANT]
>  Сбой при вызове `EndCustomDump` вызывает утечку памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структура CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [Перечисление ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
