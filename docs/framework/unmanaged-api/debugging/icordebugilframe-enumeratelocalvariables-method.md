---
title: "Метод ICorDebugILFrame::EnumerateLocalVariables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateLocalVariables
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb4e6bead1bb4933f8f9af4ffb1bfb9157a028c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="e0bc4-102">Метод ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="e0bc4-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="e0bc4-103">Получает перечислитель для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="e0bc4-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0bc4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0bc4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0bc4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e0bc4-106">[out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="e0bc4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0bc4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0bc4-107">Remarks</span></span>  
 <span data-ttu-id="e0bc4-108">`EnumerateLocalVariables`Возвращает перечислитель, который может содержать локальные переменные, доступные в кадр вызова, который представлен этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e0bc4-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e0bc4-109">Список может содержать не все локальные переменные в исполняемой функции, поскольку некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="e0bc4-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bc4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e0bc4-110">Requirements</span></span>  
 <span data-ttu-id="e0bc4-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0bc4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bc4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0bc4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0bc4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0bc4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0bc4-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0bc4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
