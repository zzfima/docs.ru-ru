---
title: Метод IHostAssemblyStore::ProvideAssembly
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8491852ea1fd9791de761d848b774480f4b461
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550296"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Метод IHostAssemblyStore::ProvideAssembly
Возвращает ссылку на сборку, которая не ссылается на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , возвращаемый методом [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Общеязыковая среда выполнения (CLR) вызывает `ProvideAssembly` для каждой сборки, которое не отображается в списке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBindInfo`  
 [in] Указатель на [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) экземпляр, который использует узел, чтобы определить характеристики привязки, включая наличие или отсутствие любой политики управления версиями и какую сборку следует привязать к.  
  
 `pAssemblyId`  
 [out] Указатель на уникальный идентификатор запрошенной сборки для данного `IStream`.  
  
 `pHostContext`  
 [out] Указатель на данные, зависящие от узла, используемый для определения свидетельство запрошенной сборки без необходимости платформы вызова неуправляемого кода. `pHostContext` соответствует <xref:System.Reflection.Assembly.HostContext%2A> свойство управляемых <xref:System.Reflection.Assembly> класса.  
  
 `ppStmAssemblyImage`  
 [out] Указатель на адрес `IStream` , содержащий изображение переносимого исполняемого (PE), загрузить, или значение null, если не удалось найти сборку.  
  
 `ppStmPDB`  
 [out] Указатель на адрес `IStream` , содержащий сведения о программе отладки (PDB), или значение null, если не удается найти PDB-файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку.|  
|E_NOT_SUFFICIENT_BUFFER|Размер буфера, указанный параметром `pAssemblyId` недостаточно велик для хранения идентификатора, который необходимо вернуть.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение identity для `pAssemblyId` указанным хостом. Идентификаторы должны быть уникальными в пределах времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора для потока. Она проверяет каждое значение со значениями для `pAssemblyId` возвращаемые других вызовов `ProvideAssembly`. Если узел возвращает тот же `pAssemblyId` значение для другого `IStream`, среда CLR проверяет ли содержимое этого потока уже были сопоставлены. Если Да, среда выполнения загружает имеющуюся копию образа вместо сопоставления нового.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
