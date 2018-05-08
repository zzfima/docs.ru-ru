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
ms.openlocfilehash: e32d48931177a42dd14092b4052370764a217abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Метод IHostAssemblyStore::ProvideAssembly
Возвращает ссылку на сборку, которая не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращенный [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Общеязыковая среда выполнения (CLR) вызывает `ProvideAssembly` для каждой сборки, которое не отображается в списке.  
  
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
 [in] Указатель на [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) экземпляр, который узел использует для определения характеристики привязки, включая наличие или отсутствие все политики управления версиями и какие сборки для привязки.  
  
 `pAssemblyId`  
 [out] Указатель на уникальный идентификатор для запрашиваемой сборки для данного `IStream`.  
  
 `pHostContext`  
 [out] Указатель на данные определенного узла, используемый для определения свидетельство запрошенную сборку без необходимости платформы вызова неуправляемого кода. `pHostContext` соответствует <xref:System.Reflection.Assembly.HostContext%2A> свойство управляемых <xref:System.Reflection.Assembly> класса.  
  
 `ppStmAssemblyImage`  
 [out] Указатель на адрес `IStream` , содержащий изображение переносимого исполняемого (PE) загружена, либо значение null, если не удалось найти сборку.  
  
 `ppStmPDB`  
 [out] Указатель на адрес `IStream` , содержащий сведения о программе отладки (PDB), или значение null, если не удается найти PDB-файл.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0X80070002)|Не удалось найти запрошенную сборку.|  
|E_NOT_SUFFICIENT_BUFFER|Размер буфера, заданный свойством `pAssemblyId` недостаточно велик для хранения с идентификатором, который необходимо вернуть.|  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение идентификатора для `pAssemblyId` заданный главным узлом. Идентификаторы должны быть уникальными в пределах срока существования процесса. Среда CLR использует это значение в качестве уникального идентификатора для потока. Она проверяет каждое значение со значениями параметра `pAssemblyId` возвращенных другими вызовами `ProvideAssembly`. Если узел возвращает тот же `pAssemblyId` значение для другого `IStream`, среда CLR проверяет, является ли содержимое этого потока уже были сопоставлены. В этом случае среда выполнения загружает имеющуюся копию образа вместо сопоставления нового.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
