---
title: Метод ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e78b8a2069671d0fe790956ca914225325a78bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228826"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="1efd6-102">Метод ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="1efd6-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="1efd6-103">Получает полный XML-потока, связанного с управляемый помощник по отладке (MDA), представленный [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1efd6-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1efd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1efd6-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1efd6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1efd6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1efd6-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="1efd6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1efd6-107">[out] Указатель на длину потока XML.</span><span class="sxs-lookup"><span data-stu-id="1efd6-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="1efd6-108">[out] Массив, в котором будет храниться поток XML.</span><span class="sxs-lookup"><span data-stu-id="1efd6-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="1efd6-109">Массив может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="1efd6-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1efd6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1efd6-110">Remarks</span></span>  
 <span data-ttu-id="1efd6-111">`GetXML` Метод могут повлиять на производительность, в зависимости от размера связанного потока XML.</span><span class="sxs-lookup"><span data-stu-id="1efd6-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1efd6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1efd6-112">Requirements</span></span>  
 <span data-ttu-id="1efd6-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1efd6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1efd6-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1efd6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1efd6-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1efd6-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1efd6-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1efd6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1efd6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1efd6-117">See also</span></span>

- [<span data-ttu-id="1efd6-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="1efd6-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="1efd6-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="1efd6-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
