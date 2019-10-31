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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124491"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>Метод IHostAssemblyStore::ProvideAssembly
Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , возвращаемую из [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Среда CLR вызывает `ProvideAssembly` для каждой сборки, которая не отображается в списке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBindInfo`  
 окне Указатель на экземпляр [ассемблибиндинфо](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) , используемый узлом для определения определенных характеристик привязки, включая присутствие или отсутствие политики управления версиями, а также сборку, к которой необходимо выполнить привязку.  
  
 `pAssemblyId`  
 заполняет Указатель на уникальный идентификатор для запрошенной сборки для этого `IStream`.  
  
 `pHostContext`  
 заполняет Указатель на данные конкретного узла, который используется для определения свидетельства запрошенной сборки без вызова неуправляемого кода. `pHostContext` соответствует свойству <xref:System.Reflection.Assembly.HostContext%2A> управляемого класса <xref:System.Reflection.Assembly>.  
  
 `ppStmAssemblyImage`  
 заполняет Указатель на адрес `IStream`, который содержит загружаемый переносимый исполняемый файл (PE), или значение null, если сборку найти не удалось.  
  
 `ppStmPDB`  
 заполняет Указатель на адрес `IStream`, который содержит сведения об отладке программы (PDB), или значение null, если PDB-файл найти не удалось.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|Не удалось найти запрошенную сборку.|  
|E_NOT_SUFFICIENT_BUFFER|Размер буфера, указанный `pAssemblyId`, недостаточно велик для хранения идентификатора, который требуется вернуть узлу.|  
  
## <a name="remarks"></a>Заметки  
 Значение идентификатора, возвращаемое для `pAssemblyId`, задается узлом. Идентификаторы должны быть уникальными в течение всего времени существования процесса. Среда CLR использует это значение в качестве уникального идентификатора потока. Он проверяет каждое значение на соответствие значениям `pAssemblyId`, возвращаемых другими вызовами метода `ProvideAssembly`. Если узел возвращает одно и то же значение `pAssemblyId` для другого `IStream`, среда CLR проверяет, было ли уже сопоставлено содержимое этого потока. Если это так, среда выполнения загружает существующую копию изображения вместо сопоставления нового.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
