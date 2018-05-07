---
title: Метод ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 895c8bc7b550fd063a9215c60f10f183e24bac83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugassembly2isfullytrusted-method"></a>Метод ICorDebugAssembly2::IsFullyTrusted
Возвращает значение, указывающее, является ли сборки было предоставлено полное доверие система безопасности среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbFullyTrusted`  
 [out] `true` , если сборки был предоставлен полный уровень доверия, система безопасности среды выполнения; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешены, то есть, если код не в сборке еще не выполнялся.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
