---
title: "Метод IMetaDataEmit::SetHandler"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetHandler
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4a56db43f932a155b4251f019e39dc5640eb014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsethandler-method"></a>Метод IMetaDataEmit::SetHandler
Задает метод, который ссылается заданный дескриптор `IUnknown` указатель в виде обратного вызова уведомления для повторного сопоставления маркера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pUnk`  
 [in] Обработчик для регистрации.  
  
## <a name="remarks"></a>Примечания  
 Ядро метаданных отправляет уведомление с помощью метода, предоставляемая `SetHandler`, для компиляторов, не создает записи оптимальным образом и который вы хотите оптимизировать сохраненных записей.  
  
 Если метод обратного вызова не предоставляется через `SetHandler`, будет выполняться без оптимизации на сохранить за исключением того, где несколько импорта области были объединены с помощью `IMapToken` на слияния для каждой области.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
