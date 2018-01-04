---
title: "Метод IHostAssemblyStore::ProvideModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b29f19933ae985d15627d1eba2622f350a52e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Метод IHostAssemblyStore::ProvideModule
Разрешает модулю в сборке или связанный (но не внедренный) файла ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBindInfo`  
 [in] Указатель на [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) экземпляр, описывающий запрошенный модуль <xref:System.AppDomain>, сборки и имя модуля.  
  
 `pdwModuleId`  
 [out] Указатель на уникальный идентификатор для `IStream` содержащий загруженного модуля.  
  
 `ppStmModuleImage`  
 [out] Указатель на адрес `IStream` объект, содержащий переносимого исполняемого (PE) образа загрузки, или значение null, если модуль не найден.  
  
 `ppStmPDB`  
 [out] Указатель на адрес объекта `IStream` объекта, который содержит программы (PDB) отладки для запрошенного модуля, или значение null, если не удалось найти PDB-файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideModule`успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0X80070002)|Не удалось найти запрошенную сборку или связанный ресурс.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId`недостаточно велик для хранения идентификатора, который необходимо вернуть.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение идентификатора для `pdwModuleId` заданный главным узлом. Идентификаторы должны быть уникальными в пределах срока существования процесса. Среда CLR использует это значение как уникальный идентификатор для соответствующего потока. Она проверяет каждое значение со значениями параметра `pAssemblyId` возвращается путем вызова метода [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) и со значениями параметра `pdwModuleId` возвращенных другими вызовами `ProvideModule`. Если узел возвращает то же значение идентификатора для другого `IStream`, среда CLR проверяет, является ли содержимое этого потока уже были сопоставлены. В этом случае среда CLR загружает имеющуюся копию образа вместо сопоставления нового. Таким образом, идентификатор также не должен перекрывать идентификаторы сборки, возвращенные `ProvideAssembly`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
