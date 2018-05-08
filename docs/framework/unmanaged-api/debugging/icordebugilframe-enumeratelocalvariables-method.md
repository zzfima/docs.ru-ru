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
ms.openlocfilehash: 6fd7694901534ad6897bbf78239081af6314e4bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>Метод ICorDebugILFrame::EnumerateLocalVariables
Получает перечислитель для локальных переменных в кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppValueEnum`  
 [out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.  
  
## <a name="remarks"></a>Примечания  
 `EnumerateLocalVariables` Возвращает перечислитель, который может содержать локальные переменные, доступные в кадр вызова, который представлен этим объектом ICorDebugILFrame. Список может содержать не все локальные переменные в исполняемой функции, поскольку некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
