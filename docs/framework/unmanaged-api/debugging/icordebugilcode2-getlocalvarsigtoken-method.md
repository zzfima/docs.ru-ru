---
title: "Метод ICorDebugILCode2::GetLocalVarSigToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d41b60e5fb528dfba0f7fa82d7792a1f08ba915
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="7d0f2-102">Метод ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="7d0f2-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="7d0f2-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="7d0f2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7d0f2-104">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="7d0f2-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d0f2-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d0f2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d0f2-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="7d0f2-107">[из] Указатель на маркер `mdSignature` для подписи локальной переменной, предназначенной для этой функции, или `mdSignatureNil`, если подпись отсутствует (т. е. если функция не имеет локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="7d0f2-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d0f2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d0f2-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d0f2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7d0f2-109">Requirements</span></span>  
 <span data-ttu-id="7d0f2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d0f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d0f2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d0f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d0f2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d0f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d0f2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d0f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0f2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7d0f2-114">See Also</span></span>  
 [<span data-ttu-id="7d0f2-115">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="7d0f2-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="7d0f2-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7d0f2-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
