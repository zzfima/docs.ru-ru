---
title: 'Метод IcorDebugVariableHome:: Жетливеранже'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: a8b8955d2f4c164031974f0d9021fb766ff2c030
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125117"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="1e956-102">Метод IcorDebugVariableHome:: Жетливеранже</span><span class="sxs-lookup"><span data-stu-id="1e956-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="1e956-103">Возвращает собственный диапазон, в котором эта переменная находится в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="1e956-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e956-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e956-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e956-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e956-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="1e956-106">заполняет Логическое смещение, при котором переменная впервые находится в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="1e956-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="1e956-107">заполняет Логическое смещение сразу после точки, в которой переменная была последней динамической.</span><span class="sxs-lookup"><span data-stu-id="1e956-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e956-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1e956-108">Requirements</span></span>  
 <span data-ttu-id="1e956-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e956-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e956-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e956-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e956-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e956-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e956-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e956-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e956-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1e956-113">See also</span></span>

- [<span data-ttu-id="1e956-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="1e956-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
