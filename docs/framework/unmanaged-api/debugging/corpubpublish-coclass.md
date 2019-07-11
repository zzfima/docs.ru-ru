---
title: Кокласс CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d1ca8ea9d00de8a07c67977cf108c50268802e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739354"
---
# <a name="corpubpublish-coclass"></a>Кокласс CorpubPublish
Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Предоставляет методы для публикации информации о процессах и домены приложений в этих процессах.|  
|[Интерфейс ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Представляет и предоставляет сведения о домене приложения в процессе.|  
|[Интерфейс ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Предоставляет методы, выполняющие перебор коллекции доменов приложений, которые в настоящее время существует внутри процесса.|  
|[Интерфейс ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Представляет процесс, который выполняется на компьютере.|  
|[Интерфейс ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Предоставляет методы, выполняющие перебор коллекции процессов, запущенных на компьютере.|  
  
## <a name="remarks"></a>Примечания  
 Типичный сценарий публикации включает в себя разработчик, которому необходимо произвести отладку управляемого кода, на котором выполняется на компьютере в домене приложения. Среда размещения может выполняться несколько доменов приложений внутри процесса. Разработчик хотел использовать графический пользовательский интерфейс или другими средствами, чтобы получить список всех процессов, запущенных на компьютере, а затем выбрать определенный процесс. Список должен включать все домены приложений в процессы, работающие в управляемом коде. Разработчик можно определить домен определенное приложение и подключить отладчик к этому домену.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorPub.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
