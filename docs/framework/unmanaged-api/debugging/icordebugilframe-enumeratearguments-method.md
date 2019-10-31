---
title: Метод ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131029"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="e9af9-102">Метод ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="e9af9-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="e9af9-103">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="e9af9-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9af9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9af9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9af9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9af9-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e9af9-106">заполняет Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="e9af9-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9af9-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e9af9-107">Remarks</span></span>  
 <span data-ttu-id="e9af9-108">`EnumerateArguments` Получает перечислитель, который может перечислить аргументы, доступные в кадре вызова, представленном этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e9af9-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e9af9-109">Список будет содержать аргументы [vararg](/cpp/windows/vararg) (то есть переменное число аргументов), а также аргументы, которые не `vararg`.</span><span class="sxs-lookup"><span data-stu-id="e9af9-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9af9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e9af9-110">Requirements</span></span>  
 <span data-ttu-id="e9af9-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9af9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9af9-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9af9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9af9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9af9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9af9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9af9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
