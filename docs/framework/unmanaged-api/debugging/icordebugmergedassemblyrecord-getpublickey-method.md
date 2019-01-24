---
title: Метод ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2b7c2f70b4776c5448d23f37c520bb5b07c051e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541655"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="72381-102">Метод ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="72381-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="72381-103">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="72381-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72381-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72381-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72381-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72381-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="72381-106">[in] Максимальное число байтов в массиве `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="72381-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="72381-107">[out] Указатель на фактическое число байтов, записанных в массив `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="72381-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="72381-108">[out] Указатель на массив байтов, содержащий открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="72381-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72381-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="72381-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72381-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="72381-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72381-111">Требования</span><span class="sxs-lookup"><span data-stu-id="72381-111">Requirements</span></span>  
 <span data-ttu-id="72381-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72381-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72381-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72381-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72381-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72381-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72381-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72381-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72381-116">См. также</span><span class="sxs-lookup"><span data-stu-id="72381-116">See also</span></span>
- [<span data-ttu-id="72381-117">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="72381-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="72381-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="72381-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
