---
title: "Метод ICorPublishProcess::IsManaged"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 622781a6c1ad5d5efa3bb2d5227c4f5b845bf94e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessismanaged-method"></a>Метод ICorPublishProcess::IsManaged
Возвращает значение, указывающее, является ли процесс ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) известен управляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbManaged`  
 [out] Указатель на значение Boolean, указывающее, является ли процесс с управляемым кодом. Значение равно `true` Если процесс с управляемым кодом; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Так как текущая версия `ICorPublishProcess` разрешает доступ только к процессам, которые управляемый код, `IsManaged` всегда возвращает `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorPublishProcess-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
