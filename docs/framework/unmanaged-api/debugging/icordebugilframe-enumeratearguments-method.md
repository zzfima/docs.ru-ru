---
title: "Метод ICorDebugILFrame::EnumerateArguments"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateArguments
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf345f3fa684b57a33e3452916535b1cd7db3c8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="c8988-102">Метод ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="c8988-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="c8988-103">Получает перечислитель для аргументов в кадре.</span><span class="sxs-lookup"><span data-stu-id="c8988-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8988-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8988-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8988-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8988-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="c8988-106">[out] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="c8988-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8988-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8988-107">Remarks</span></span>  
 <span data-ttu-id="c8988-108">`EnumerateArguments`Возвращает перечислитель, который может содержать аргументы, доступных в кадр вызова, который представлен этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="c8988-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="c8988-109">В списке будут содержаться аргументы, которые являются [vararg](/cpp/windows/vararg) (то есть с переменным числом аргументов) и аргументы, которые не являются `vararg`.</span><span class="sxs-lookup"><span data-stu-id="c8988-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8988-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c8988-110">Requirements</span></span>  
 <span data-ttu-id="c8988-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8988-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8988-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8988-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8988-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8988-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8988-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8988-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
