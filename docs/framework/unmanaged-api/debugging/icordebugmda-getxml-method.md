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
ms.openlocfilehash: 874462e37aa10af589f39ed099de899ff7155d24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414649"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="ecc72-102">Метод ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="ecc72-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="ecc72-103">Получает полный XML-поток, связанный с управляемый помощник по отладке (MDA), представленный [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ecc72-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecc72-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecc72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecc72-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ecc72-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="ecc72-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ecc72-107">[out] Указатель на длину потока XML.</span><span class="sxs-lookup"><span data-stu-id="ecc72-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="ecc72-108">[out] Массив, в котором хранятся XML-потока.</span><span class="sxs-lookup"><span data-stu-id="ecc72-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="ecc72-109">Массив может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="ecc72-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc72-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecc72-110">Remarks</span></span>  
 <span data-ttu-id="ecc72-111">`GetXML` Метод может влиять на производительность, в зависимости от размера связанного потока XML.</span><span class="sxs-lookup"><span data-stu-id="ecc72-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc72-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ecc72-112">Requirements</span></span>  
 <span data-ttu-id="ecc72-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc72-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc72-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecc72-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecc72-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc72-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc72-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc72-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ecc72-117">See Also</span></span>  
 [<span data-ttu-id="ecc72-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="ecc72-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="ecc72-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="ecc72-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
