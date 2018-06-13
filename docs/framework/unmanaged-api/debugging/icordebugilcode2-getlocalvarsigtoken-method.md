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
ms.openlocfilehash: e02f44e4f581170a842a1c103ed069cb90cde79c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412302"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="11fc3-102">Метод ICorDebugILCode2::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="11fc3-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="11fc3-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="11fc3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="11fc3-104">Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.</span><span class="sxs-lookup"><span data-stu-id="11fc3-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11fc3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11fc3-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11fc3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="11fc3-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="11fc3-107">[из] Указатель на маркер `mdSignature` для подписи локальной переменной, предназначенной для этой функции, или `mdSignatureNil`, если подпись отсутствует (т. е. если функция не имеет локальных переменных).</span><span class="sxs-lookup"><span data-stu-id="11fc3-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11fc3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="11fc3-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11fc3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="11fc3-109">Requirements</span></span>  
 <span data-ttu-id="11fc3-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11fc3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11fc3-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11fc3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11fc3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11fc3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11fc3-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11fc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11fc3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="11fc3-114">See Also</span></span>  
 [<span data-ttu-id="11fc3-115">Интерфейс ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="11fc3-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="11fc3-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="11fc3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
