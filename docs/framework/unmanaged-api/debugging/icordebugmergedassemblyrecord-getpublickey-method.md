---
title: Метод ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: c8c6e9adcb9d29f5e234dd1b8dfd351fac575301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793121"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="5814c-102">Метод ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="5814c-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="5814c-103">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="5814c-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5814c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5814c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5814c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5814c-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="5814c-106">[in] Максимальное число байтов в массиве `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="5814c-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="5814c-107">[out] Указатель на фактическое число байтов, записанных в массив `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="5814c-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="5814c-108">[out] Указатель на массив байтов, содержащий открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="5814c-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5814c-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="5814c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5814c-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5814c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5814c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5814c-111">Requirements</span></span>  
 <span data-ttu-id="5814c-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5814c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5814c-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5814c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5814c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5814c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5814c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5814c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5814c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5814c-116">See also</span></span>

- [<span data-ttu-id="5814c-117">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="5814c-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="5814c-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5814c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
