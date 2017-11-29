---
title: "Метод ICorDebugMergedAssemblyRecord::GetPublicKeyToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c286981def6f12f8e5b8fa5397f23535d4d4623
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="3f594-102">Метод ICorDebugMergedAssemblyRecord::GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="3f594-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="3f594-103">Возвращает токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="3f594-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f594-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f594-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f594-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f594-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="3f594-106">[in] Максимальное число байтов в массиве `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="3f594-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="3f594-107">[out] Указатель на фактическое число байтов, записанных в массив `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="3f594-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="3f594-108">[out] Указатель на массив байтов, содержащий токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="3f594-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f594-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f594-109">Remarks</span></span>  
 <span data-ttu-id="3f594-110">Токен открытого ключа сборки — это последние восемь байтов хэша SHA1 ее открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="3f594-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f594-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3f594-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f594-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3f594-112">Requirements</span></span>  
 <span data-ttu-id="3f594-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f594-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f594-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f594-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f594-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f594-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f594-116">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f594-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f594-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3f594-117">See Also</span></span>  
 [<span data-ttu-id="3f594-118">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="3f594-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="3f594-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3f594-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
