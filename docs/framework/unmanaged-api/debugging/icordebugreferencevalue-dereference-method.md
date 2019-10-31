---
title: Метод ICorDebugReferenceValue::Dereference
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 6bb2a6b68a3c6e981a2d6c833d3f44d4c836bd23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124001"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="6e885-102">Метод ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="6e885-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="6e885-103">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="6e885-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e885-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e885-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e885-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e885-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="6e885-106">заполняет Указатель на адрес ICorDebugValue, представляющий объект, на который указывает объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="6e885-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e885-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6e885-107">Remarks</span></span>  
 <span data-ttu-id="6e885-108">Объект `ICorDebugValue` является допустимым только тогда, когда его ссылка еще не была отключена.</span><span class="sxs-lookup"><span data-stu-id="6e885-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e885-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6e885-109">Requirements</span></span>  
 <span data-ttu-id="6e885-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e885-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e885-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e885-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e885-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e885-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e885-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e885-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
