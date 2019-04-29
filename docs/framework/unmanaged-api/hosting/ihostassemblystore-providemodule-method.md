---
title: Метод IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599352"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Метод IHostAssemblyStore::ProvideModule
Разрешает файл ресурсов модуля в сборку или связанный (но не внедренный).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBindInfo`  
 [in] Указатель на [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) экземпляр, описывающий запрошенного модуля <xref:System.AppDomain>, сборки и имя модуля.  
  
 `pdwModuleId`  
 [out] Указатель на уникальный идентификатор для `IStream` содержащий загруженного модуля.  
  
 `ppStmModuleImage`  
 [out] Указатель на адрес `IStream` объекта, который содержит переносимого исполняемого (PE) образа загрузки, или значение null, если модуль не найден.  
  
 `ppStmPDB`  
 [out] Указатель на адрес `IStream` объекта, который содержит данные отладки (PDB) программы для запрошенного модуля, или значение null, если не удается найти PDB-файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideModule` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку или связанного ресурса.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` не является достаточным для хранения идентификатора, который необходимо вернуть.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение identity для `pdwModuleId` указанным хостом. Идентификаторы должны быть уникальными в пределах времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора для соответствующего потока. Она проверяет каждое значение со значениями для `pAssemblyId` возвращаемые вызовы [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) и со значениями для `pdwModuleId` возвращаемые других вызовов `ProvideModule`. Если узел возвращает то же значение идентификатора для другого `IStream`, среда CLR проверяет ли содержимое этого потока уже были сопоставлены. Если Да, среда CLR загружает имеющуюся копию образа вместо сопоставления нового. Таким образом, идентификатор также не должен пересекаться с идентификаторы сборки, возвращенные из `ProvideAssembly`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
