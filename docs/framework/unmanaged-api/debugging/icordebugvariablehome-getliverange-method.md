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
ms.openlocfilehash: 28e41106ffcaf1ed2ed87166e641bb5e5f447e47
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791017"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="f3b63-102">Метод IcorDebugVariableHome:: Жетливеранже</span><span class="sxs-lookup"><span data-stu-id="f3b63-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="f3b63-103">Возвращает собственный диапазон, в котором эта переменная находится в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="f3b63-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3b63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3b63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3b63-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="f3b63-106">заполняет Логическое смещение, при котором переменная впервые находится в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="f3b63-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="f3b63-107">заполняет Логическое смещение сразу после точки, в которой переменная была последней динамической.</span><span class="sxs-lookup"><span data-stu-id="f3b63-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b63-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f3b63-108">Requirements</span></span>  
 <span data-ttu-id="f3b63-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b63-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b63-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3b63-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3b63-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3b63-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3b63-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b63-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b63-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3b63-113">See also</span></span>

- [<span data-ttu-id="f3b63-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="f3b63-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
