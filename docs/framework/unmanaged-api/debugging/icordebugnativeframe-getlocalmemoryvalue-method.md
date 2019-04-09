---
title: Метод ICorDebugNativeFrame::GetLocalMemoryValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c44f3e369ac64773811a6aea74756783dedd2fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209467"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="e20c1-102">Метод ICorDebugNativeFrame::GetLocalMemoryValue</span><span class="sxs-lookup"><span data-stu-id="e20c1-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="e20c1-103">Получает значение аргумента или локальной переменной, которая хранится в заданном расположении памяти для данного кадра машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e20c1-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e20c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e20c1-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e20c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e20c1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e20c1-106">[in] Объект `CORDB_ADDRESS` значение, указывающее область памяти, содержащий значение.</span><span class="sxs-lookup"><span data-stu-id="e20c1-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e20c1-107">[in] Целое число, указывающее размер двоичную подпись метаданных которого ссылается `pvSigBlob` параметра.</span><span class="sxs-lookup"><span data-stu-id="e20c1-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e20c1-108">[in] Объект `PCCOR_SIGNATURE` значение, которое указывает на двоичную подпись метаданных типа значения.</span><span class="sxs-lookup"><span data-stu-id="e20c1-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e20c1-109">[out] Указатель на адрес объекта «ICorDebugValue», представляющего извлеченное значение, которое хранится в указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="e20c1-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e20c1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e20c1-110">Requirements</span></span>  
 <span data-ttu-id="e20c1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e20c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e20c1-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e20c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e20c1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e20c1-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e20c1-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e20c1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e20c1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e20c1-115">See also</span></span>
