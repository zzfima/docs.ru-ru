---
title: Метод ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134675"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="2ad1d-102">Метод ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="2ad1d-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="2ad1d-103">Возвращает значение, указывающее, присоединен ли отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="2ad1d-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ad1d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad1d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ad1d-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="2ad1d-106">[out] `true`, если отладчик присоединен к домену приложения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2ad1d-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ad1d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="2ad1d-107">Remarks</span></span>  
 <span data-ttu-id="2ad1d-108">Методы ICorDebugController нельзя использовать до тех пор, пока отладчик не подключится к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="2ad1d-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad1d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2ad1d-109">Requirements</span></span>  
 <span data-ttu-id="2ad1d-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad1d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad1d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ad1d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ad1d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ad1d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ad1d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad1d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
