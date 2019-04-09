---
title: Метод ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610e46d5cb550a266c5558c49239d1818c1e85de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107280"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="00756-102">Метод ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="00756-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="00756-103">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="00756-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00756-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00756-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00756-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00756-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="00756-106">[in] Максимальное число байтов в массиве `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="00756-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="00756-107">[out] Указатель на фактическое число байтов, записанных в массив `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="00756-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="00756-108">[out] Указатель на массив байтов, содержащий открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="00756-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00756-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="00756-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00756-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="00756-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00756-111">Требования</span><span class="sxs-lookup"><span data-stu-id="00756-111">Requirements</span></span>  
 <span data-ttu-id="00756-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00756-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00756-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00756-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00756-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00756-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="00756-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="00756-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00756-116">См. также</span><span class="sxs-lookup"><span data-stu-id="00756-116">See also</span></span>

- [<span data-ttu-id="00756-117">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="00756-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="00756-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="00756-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
