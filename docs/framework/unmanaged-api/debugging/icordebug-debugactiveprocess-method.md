---
title: Метод ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 2d71cebb77ed3ca586e857710667c0077f4f76ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793584"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="6b7d9-102">Метод ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="6b7d9-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="6b7d9-103">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="6b7d9-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b7d9-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b7d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b7d9-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6b7d9-106">окне Идентификатор процесса, к которому должен быть присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="6b7d9-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="6b7d9-107">окне Логическое значение, которое устанавливается в `true`, если отладчик должен вести себя в качестве отладчика Win32 для процесса и отправляют неуправляемые обратные вызовы. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="6b7d9-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="6b7d9-108">заполняет Указатель на адрес объекта "ICorDebugProcess", который представляет процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="6b7d9-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b7d9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6b7d9-109">Remarks</span></span>  
 <span data-ttu-id="6b7d9-110">Отладка взаимодействия не поддерживается на платформах Win9x и на платформе, отличной от x86, например на платформах на основе IA-64 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="6b7d9-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b7d9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b7d9-111">Requirements</span></span>  
 <span data-ttu-id="6b7d9-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b7d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b7d9-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b7d9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b7d9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b7d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b7d9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b7d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7d9-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b7d9-116">See also</span></span>

- [<span data-ttu-id="6b7d9-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="6b7d9-117">ICorDebug Interface</span></span>](icordebug-interface.md)
