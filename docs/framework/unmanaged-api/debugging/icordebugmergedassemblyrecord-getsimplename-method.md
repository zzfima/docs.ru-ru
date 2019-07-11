---
title: Метод ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3df84fa7c316d3cd0c97b79478159a5a97ad1e64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762362"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="80900-102">Метод ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="80900-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="80900-103">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="80900-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80900-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80900-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80900-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80900-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="80900-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="80900-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="80900-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="80900-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="80900-108">Указатель на массив символов.</span><span class="sxs-lookup"><span data-stu-id="80900-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80900-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="80900-109">Remarks</span></span>  
 <span data-ttu-id="80900-110">Этот метод возвращает простое имя сборки (например, System.Collections) без расширения имени файла, версии, языка и региональных параметров и токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="80900-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="80900-111">Оно соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="80900-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80900-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="80900-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80900-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80900-113">Requirements</span></span>  
 <span data-ttu-id="80900-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80900-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80900-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80900-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80900-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80900-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80900-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80900-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80900-118">См. также</span><span class="sxs-lookup"><span data-stu-id="80900-118">See also</span></span>

- [<span data-ttu-id="80900-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="80900-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="80900-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="80900-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
