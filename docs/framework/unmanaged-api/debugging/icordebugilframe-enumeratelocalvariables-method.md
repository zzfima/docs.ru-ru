---
title: Метод ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cc9601105d05740e6db0a41bae521bd9a276d74
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471320"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>Метод ICorDebugILFrame::EnumerateLocalVariables
Получает перечислитель для локальных переменных в кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppValueEnum`  
 [out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в кадре.  
  
## <a name="remarks"></a>Примечания  
 `EnumerateLocalVariables` Возвращает перечислитель, который можно вывести список локальных переменных, доступных в кадр вызова, который представлен этим объектом ICorDebugILFrame. Список может содержать не все локальные переменные в исполняемой функции, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
