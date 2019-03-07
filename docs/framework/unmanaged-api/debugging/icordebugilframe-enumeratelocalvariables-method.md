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
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="f97a4-102">Метод ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="f97a4-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="f97a4-103">Получает перечислитель для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="f97a4-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f97a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f97a4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f97a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f97a4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="f97a4-106">[out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="f97a4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f97a4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f97a4-107">Remarks</span></span>  
 <span data-ttu-id="f97a4-108">`EnumerateLocalVariables` Возвращает перечислитель, который можно вывести список локальных переменных, доступных в кадр вызова, который представлен этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="f97a4-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="f97a4-109">Список может содержать не все локальные переменные в исполняемой функции, так как некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="f97a4-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f97a4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f97a4-110">Requirements</span></span>  
 <span data-ttu-id="f97a4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f97a4-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f97a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f97a4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f97a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f97a4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f97a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
