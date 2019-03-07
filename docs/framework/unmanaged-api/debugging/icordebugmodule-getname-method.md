---
title: Метод ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: efbcd6f9eca426cd230653e38d527e184b378fa0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503155"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="dedbd-102">Метод ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="dedbd-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="dedbd-103">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="dedbd-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dedbd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dedbd-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dedbd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dedbd-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="dedbd-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="dedbd-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dedbd-107">[in] Указатель на длину возвращаемого имени.</span><span class="sxs-lookup"><span data-stu-id="dedbd-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="dedbd-108">[out] Массив, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="dedbd-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dedbd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="dedbd-109">Remarks</span></span>  
 <span data-ttu-id="dedbd-110">`GetName` Метод возвращает значение S_OK HRESULT, если имя файла модуля соответствует имени на диске.</span><span class="sxs-lookup"><span data-stu-id="dedbd-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="dedbd-111">`GetName` Возвращает значение HRESULT S_FALSE, если оно создано, например, модуль динамический или в памяти.</span><span class="sxs-lookup"><span data-stu-id="dedbd-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dedbd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dedbd-112">Requirements</span></span>  
 <span data-ttu-id="dedbd-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dedbd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dedbd-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dedbd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dedbd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dedbd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dedbd-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dedbd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedbd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="dedbd-117">See also</span></span>


