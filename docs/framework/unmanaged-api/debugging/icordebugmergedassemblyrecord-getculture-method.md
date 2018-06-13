---
title: Метод ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2336c89a32b202c4226f1ed194d786be6fa020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415361"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="ac9f2-102">Метод ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="ac9f2-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="ac9f2-103">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="ac9f2-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac9f2-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac9f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac9f2-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="ac9f2-106">[in] Число символов в буфере `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="ac9f2-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="ac9f2-107">[выходной] Число символов, фактически записанных в буфер `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="ac9f2-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="ac9f2-108">[выходной] Массив символов, содержащий название языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ac9f2-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9f2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac9f2-109">Remarks</span></span>  
 <span data-ttu-id="ac9f2-110">Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="ac9f2-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac9f2-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ac9f2-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9f2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ac9f2-112">Requirements</span></span>  
 <span data-ttu-id="ac9f2-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9f2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9f2-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac9f2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac9f2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac9f2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac9f2-116">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9f2-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9f2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ac9f2-117">See Also</span></span>  
 [<span data-ttu-id="ac9f2-118">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ac9f2-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="ac9f2-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ac9f2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
