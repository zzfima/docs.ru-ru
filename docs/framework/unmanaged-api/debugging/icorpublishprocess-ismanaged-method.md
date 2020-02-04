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
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790529"
---
# <a name="icorpublishprocessismanaged-method"></a>Метод ICorPublishProcess::IsManaged
Возвращает значение, указывающее, известно ли для процесса, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md) , управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbManaged`  
 заполняет Указатель на логическое значение, указывающее, имеет ли процесс управляемый код. Значение `true`, если процесс имеет управляемый код; в противном случае `false`.  
  
## <a name="remarks"></a>Заметки  
 Поскольку текущая версия `ICorPublishProcess` разрешает доступ только к процессам с управляемым кодом, `IsManaged` всегда возвращает `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)
