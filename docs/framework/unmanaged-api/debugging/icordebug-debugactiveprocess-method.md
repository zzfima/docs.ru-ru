---
title: "Метод ICorDebug::DebugActiveProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.DebugActiveProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c17345caaec71e4d4b057bdcfc2cc395014cbf82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="65058-102">Метод ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="65058-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="65058-103">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="65058-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65058-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65058-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65058-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65058-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="65058-106">[in] Идентификатор процесса, в котором отладчик должен быть связан.</span><span class="sxs-lookup"><span data-stu-id="65058-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="65058-107">[in] Логическое значение, равное `true` Если отладчик должен ведут себя как отладчик Win32 для процесса и направление неуправляемые обратных вызовов; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="65058-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="65058-108">[out] Указатель на адрес объекта «ICorDebugProcess», который представляет собой процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="65058-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65058-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="65058-109">Remarks</span></span>  
 <span data-ttu-id="65058-110">Отладка взаимодействия не поддерживается на платформах Win9x и не x86, например основе AMD64 и IA-64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="65058-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65058-111">Требования</span><span class="sxs-lookup"><span data-stu-id="65058-111">Requirements</span></span>  
 <span data-ttu-id="65058-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65058-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65058-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65058-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65058-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65058-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65058-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65058-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65058-116">См. также</span><span class="sxs-lookup"><span data-stu-id="65058-116">See Also</span></span>  
 [<span data-ttu-id="65058-117">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="65058-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
