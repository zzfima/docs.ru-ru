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
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124470"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>Метод IHostAssemblyStore::ProvideModule
Разрешает модуль в сборке или связанном (но не внедренном) файле ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBindInfo`  
 окне Указатель на экземпляр [модулебиндинфо](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) , описывающий <xref:System.AppDomain>, сборку и имя модуля запрошенного модуля.  
  
 `pdwModuleId`  
 заполняет Указатель на уникальный идентификатор для `IStream`, содержащего загруженный модуль.  
  
 `ppStmModuleImage`  
 заполняет Указатель на адрес объекта `IStream`, который содержит загружаемый переносимый исполняемый образ (PE), или значение null, если не удалось найти модуль.  
  
 `ppStmPDB`  
 заполняет Указатель на адрес объекта `IStream`, который содержит сведения о программе отладки (PDB) для запрошенного модуля, или значение null, если PDB-файл найти не удалось.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideModule` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку или связанный ресурс.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` недостаточно велик, чтобы вместить идентификатор, который требуется вернуть узлу.|  
  
## <a name="remarks"></a>Заметки  
 Значение идентификатора, возвращаемое для `pdwModuleId`, задается узлом. Идентификаторы должны быть уникальными в течение всего времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора для связанного потока. Он проверяет каждое значение на соответствие значениям `pAssemblyId`, возвращаемых вызовами [провидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) , и значениями для `pdwModuleId`, возвращаемых другими вызовами метода `ProvideModule`. Если узел возвращает одно и то же значение идентификатора для другого `IStream`, среда CLR проверяет, было ли уже сопоставлено содержимое этого потока. Если это так, среда CLR загружает существующую копию изображения вместо сопоставления нового. Таким образом, идентификатор также не должен пересекаться с идентификаторами сборки, возвращенными из `ProvideAssembly`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
