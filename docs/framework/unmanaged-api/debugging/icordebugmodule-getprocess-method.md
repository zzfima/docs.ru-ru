---
title: Метод ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff7c77a27e9be58e9702c3a5e3f990863dc83901
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763622"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="c592a-102">Метод ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="c592a-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="c592a-103">Получает процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="c592a-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c592a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c592a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c592a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c592a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="c592a-106">[out] Указатель на адрес ICorDebugProcess объект, представляющий процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="c592a-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c592a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c592a-107">Requirements</span></span>  
 <span data-ttu-id="c592a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c592a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c592a-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c592a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c592a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c592a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c592a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c592a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
