---
title: Интерфейс ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140855"
---
# <a name="iclrmetahostpolicy-interface"></a>Интерфейс ICLRMetaHostPolicy
Предоставляет метод [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , возвращающий указатель на интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Предоставляет предпочтительный интерфейс CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.|  
  
## <a name="remarks"></a>Заметки  
 Ссылку на этот интерфейс можно получить, вызвав функцию [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) , как показано в следующем коде:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Этот интерфейс фактически не загружает и не активирует среду CLR, а просто возвращает предпочтительную версию среды CLR на основе установленных или загруженных версий.  
  
 В .NET Framework 4 API размещения консолидируются политики, чтобы узлы с конкретными потребностями могли использовать базовые функции без непреднамеренной потерь. Например, многие экспорты MSCorEE. dll привязываются к определенной среде CLR, хотя метод может не потребовать его логически. Перечисление [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) предоставляет политики привязки, общие для большинства узлов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
