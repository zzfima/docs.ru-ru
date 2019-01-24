---
title: Метод ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7bfdcc3c8328d71146732fc4ba5664ebee9bea2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574876"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="9741e-102">Метод ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="9741e-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="9741e-103">Получает значение, указывающее, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="9741e-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9741e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9741e-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9741e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9741e-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="9741e-106">[out] `true` Если этот модуль существует только в памяти; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9741e-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9741e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9741e-107">Remarks</span></span>  
 <span data-ttu-id="9741e-108">Среда CLR (CLR) поддерживает загрузку модулей из необработанных потоков байтов.</span><span class="sxs-lookup"><span data-stu-id="9741e-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="9741e-109">Такие модули называются *модули в памяти* и не существуют на диске.</span><span class="sxs-lookup"><span data-stu-id="9741e-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9741e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9741e-110">Requirements</span></span>  
 <span data-ttu-id="9741e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9741e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9741e-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9741e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9741e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9741e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9741e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9741e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9741e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9741e-115">See also</span></span>


