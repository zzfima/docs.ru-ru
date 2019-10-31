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
ms.openlocfilehash: 89af99fab1f1265701e0dbfe74a46000cb3bfaa6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132149"
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
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.|  
|[Интерфейс ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Представляет и предоставляет сведения о домене приложения в процессе.|  
|[Интерфейс ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.|  
|[Интерфейс ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Представляет процесс, выполняющийся на компьютере.|  
|[Интерфейс ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.|  
  
## <a name="remarks"></a>Заметки  
 Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения. Среда размещения может запускать несколько доменов приложений в рамках одного процесса. Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс. Список должен включать все домены приложений в процессах, выполняющих управляемый код. Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
