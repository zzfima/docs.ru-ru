---
title: Метод ICorDebugStepper::Deactivate
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd7bfb52cadf740d8fe3cb92a09b071f530b7ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417405"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="af3ff-102">Метод ICorDebugStepper::Deactivate</span><span class="sxs-lookup"><span data-stu-id="af3ff-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="af3ff-103">ICorDebugStepper для отмены последней команды шага, полученное в результате.</span><span class="sxs-lookup"><span data-stu-id="af3ff-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af3ff-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="af3ff-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="af3ff-105">Remarks</span></span>  
 <span data-ttu-id="af3ff-106">Новая команда пошагового выполнения может быть выдан после последнего полученного шаг команда была отменена.</span><span class="sxs-lookup"><span data-stu-id="af3ff-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3ff-107">Требования</span><span class="sxs-lookup"><span data-stu-id="af3ff-107">Requirements</span></span>  
 <span data-ttu-id="af3ff-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af3ff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af3ff-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af3ff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af3ff-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af3ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af3ff-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
