---
title: Метод ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 093b21a439b96c9fe2f971300f314d1b75527f1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207205"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="c2a86-102">Метод ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="c2a86-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="c2a86-103">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="c2a86-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2a86-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2a86-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="c2a86-106">[in] Число символов в буфере `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="c2a86-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="c2a86-107">[выходной] Число символов, фактически записанных в буфер `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="c2a86-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="c2a86-108">[выходной] Массив символов, содержащий название языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c2a86-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a86-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2a86-109">Remarks</span></span>  
 <span data-ttu-id="c2a86-110">Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="c2a86-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2a86-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c2a86-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a86-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c2a86-112">Requirements</span></span>  
 <span data-ttu-id="c2a86-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a86-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a86-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2a86-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2a86-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a86-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c2a86-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c2a86-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2a86-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c2a86-117">See also</span></span>

- [<span data-ttu-id="c2a86-118">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="c2a86-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c2a86-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c2a86-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
