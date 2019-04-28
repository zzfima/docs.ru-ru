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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d7fb1de0b2ea63c1a766023b23acc42e027af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995570"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="3c8c1-102">Метод ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="3c8c1-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="3c8c1-103">Получает перечислитель для аргументов в кадре.</span><span class="sxs-lookup"><span data-stu-id="3c8c1-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c8c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c8c1-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c8c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c8c1-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="3c8c1-106">[out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в кадре.</span><span class="sxs-lookup"><span data-stu-id="3c8c1-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c8c1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c8c1-107">Remarks</span></span>  
 <span data-ttu-id="3c8c1-108">`EnumerateArguments` Возвращает перечислитель, который можно вывести список доступных в кадр вызова, который представлен этим объектом ICorDebugILFrame аргументов.</span><span class="sxs-lookup"><span data-stu-id="3c8c1-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="3c8c1-109">В списке будут содержаться аргументы, которые являются [vararg](/cpp/windows/vararg) (то есть несколько переменных аргументов) а также аргументы, которые не являются `vararg`.</span><span class="sxs-lookup"><span data-stu-id="3c8c1-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c8c1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3c8c1-110">Requirements</span></span>  
 <span data-ttu-id="3c8c1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c8c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c8c1-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c8c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c8c1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c8c1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c8c1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c8c1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
