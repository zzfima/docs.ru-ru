---
title: "Метод ICorDebugMergedAssemblyRecord::GetSimpleName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0bf7bb3f52e76c34c03b322d7d6e82fa65adf8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="3209d-102">Метод ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="3209d-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="3209d-103">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="3209d-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3209d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3209d-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3209d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3209d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3209d-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="3209d-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3209d-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="3209d-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="3209d-108">Указатель на массив символов.</span><span class="sxs-lookup"><span data-stu-id="3209d-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3209d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3209d-109">Remarks</span></span>  
 <span data-ttu-id="3209d-110">Этот метод возвращает простое имя сборки (например, System.Collections) без расширения имени файла, версии, языка и региональных параметров и токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="3209d-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="3209d-111">Оно соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="3209d-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3209d-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3209d-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3209d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3209d-113">Requirements</span></span>  
 <span data-ttu-id="3209d-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3209d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3209d-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3209d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3209d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3209d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3209d-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3209d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3209d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3209d-118">See Also</span></span>  
 [<span data-ttu-id="3209d-119">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="3209d-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="3209d-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3209d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
