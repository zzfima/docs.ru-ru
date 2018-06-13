---
title: Метод ICorDebugClass::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c52795251b5cacebe749b1eedf918f8b20497796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402901"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="9ea85-102">Метод ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="9ea85-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="9ea85-103">Возвращает модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="9ea85-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ea85-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ea85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ea85-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="9ea85-106">[out] Указатель на адрес объекта ICorDebugModule, представляющий модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="9ea85-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea85-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9ea85-107">Requirements</span></span>  
 <span data-ttu-id="9ea85-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea85-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea85-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ea85-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ea85-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ea85-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ea85-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea85-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
