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
ms.openlocfilehash: 24d245bbb0f9ac86e321491e0af3b66b1e011baa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789220"
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
|[Интерфейс ICorPublish](icorpublish-interface.md)|Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.|  
|[Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)|Представляет и предоставляет сведения о домене приложения в процессе.|  
|[Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)|Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.|  
|[Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)|Представляет процесс, выполняющийся на компьютере.|  
|[Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)|Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.|  
  
## <a name="remarks"></a>Заметки  
 Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения. Среда размещения может запускать несколько доменов приложений в рамках одного процесса. Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс. Список должен включать все домены приложений в процессах, выполняющих управляемый код. Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Отладка](index.md)
