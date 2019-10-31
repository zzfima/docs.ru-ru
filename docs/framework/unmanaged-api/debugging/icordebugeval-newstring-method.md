---
title: Метод ICorDebugEval::NewString
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137644"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="a1d68-102">Метод ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="a1d68-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="a1d68-103">Выделяет новый экземпляр строки с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="a1d68-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1d68-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d68-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1d68-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="a1d68-106">окне Указатель на содержимое строки.</span><span class="sxs-lookup"><span data-stu-id="a1d68-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1d68-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a1d68-107">Remarks</span></span>  
 <span data-ttu-id="a1d68-108">Строка всегда создается в домене приложения, в котором в данный момент выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="a1d68-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d68-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a1d68-109">Requirements</span></span>  
 <span data-ttu-id="a1d68-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1d68-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d68-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1d68-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1d68-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1d68-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1d68-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
