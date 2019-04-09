---
title: Метод ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df142ea8f02d5cefc5c63a2d376afb331b4379ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197988"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="f6d90-102">Метод ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="f6d90-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="f6d90-103">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="f6d90-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6d90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6d90-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6d90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6d90-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f6d90-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6d90-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f6d90-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6d90-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f6d90-108">Указатель на массив символов.</span><span class="sxs-lookup"><span data-stu-id="f6d90-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6d90-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6d90-109">Remarks</span></span>  
 <span data-ttu-id="f6d90-110">Этот метод возвращает простое имя сборки (например, System.Collections) без расширения имени файла, версии, языка и региональных параметров и токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="f6d90-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="f6d90-111">Оно соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="f6d90-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6d90-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f6d90-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6d90-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f6d90-113">Requirements</span></span>  
 <span data-ttu-id="f6d90-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6d90-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6d90-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6d90-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6d90-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6d90-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f6d90-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f6d90-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6d90-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f6d90-118">See also</span></span>

- [<span data-ttu-id="f6d90-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f6d90-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f6d90-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f6d90-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
