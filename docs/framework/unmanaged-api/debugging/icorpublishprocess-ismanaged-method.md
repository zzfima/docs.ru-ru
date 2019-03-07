---
title: Метод ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404403576b7fd32362a690d470a5ea4b48489d26
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484801"
---
# <a name="icorpublishprocessismanaged-method"></a>Метод ICorPublishProcess::IsManaged
Получает значение, указывающее, является ли процесс ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) известно, что есть управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbManaged`  
 [out] Указатель на логическое значение, указывающее, ли процесс управляемого кода. Значение равно `true` Если процесс с управляемым кодом; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Так как текущая версия `ICorPublishProcess` разрешает доступ только к процессам, которые управляемого кода, `IsManaged` всегда возвращает `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
