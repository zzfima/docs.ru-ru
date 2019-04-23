---
title: Метод ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9810a8a55fc9c5296bffa5106551f9734dcd61bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199912"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="e5d19-102">Метод ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="e5d19-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="e5d19-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="e5d19-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e5d19-104">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="e5d19-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d19-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5d19-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5d19-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5d19-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="e5d19-107">[из] Указатель на маркер `mdSignature` для подписи локальной переменной, предназначенной для этой функции, или `mdSignatureNil`, если подпись отсутствует (т. е. если функция не имеет локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="e5d19-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5d19-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5d19-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d19-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e5d19-109">Requirements</span></span>  
 <span data-ttu-id="e5d19-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5d19-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d19-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5d19-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5d19-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5d19-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5d19-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d19-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d19-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e5d19-114">See also</span></span>

- [<span data-ttu-id="e5d19-115">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="e5d19-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="e5d19-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e5d19-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
