---
title: "Компонентный класс CorpubPublish"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a>Кокласс CorpubPublish
Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|[ICorPublish-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессов.|  
|[ICorPublishAppDomain-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|Представляет и предоставляет сведения о домен приложения в процессе.|  
|[ICorPublishAppDomainEnum-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|Предоставляет методы, выполняющие перебор коллекции доменов приложений, которые в настоящее время существует внутри процесса.|  
|[ICorPublishProcess-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|Представляет процесс, который выполняется на компьютере.|  
|[ICorPublishProcessEnum-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|Предоставляет методы, выполняющие перебор коллекции процессов, запущенных на компьютере.|  
  
## <a name="remarks"></a>Примечания  
 Типичный сценарий публикации подразумевает разработчик, которому необходимо произвести отладку управляемого кода, запущенного на компьютере в домене приложения. Среда размещения может выполняться несколько доменов приложений внутри процесса. Разработчик хотел бы использовать графический пользовательский интерфейс или другими средствами, чтобы получить список всех процессов, запущенных на компьютере и выбирать процессы. Список должен включать всех доменов приложений внутри процессов, запущенных в управляемом коде. Разработчик можно определить домен определенное приложение и подключить отладчик к этому домену.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
