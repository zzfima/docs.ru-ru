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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415474"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="50a8e-102">Метод ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="50a8e-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="50a8e-103">Получает перечислитель для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="50a8e-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50a8e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50a8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50a8e-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="50a8e-106">[out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="50a8e-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50a8e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="50a8e-107">Remarks</span></span>  
 <span data-ttu-id="50a8e-108">`EnumerateLocalVariables` Возвращает перечислитель, который может содержать локальные переменные, доступные в кадр вызова, который представлен этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="50a8e-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="50a8e-109">Список может содержать не все локальные переменные в исполняемой функции, поскольку некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="50a8e-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a8e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="50a8e-110">Requirements</span></span>  
 <span data-ttu-id="50a8e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50a8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a8e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50a8e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50a8e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a8e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a8e-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a8e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
