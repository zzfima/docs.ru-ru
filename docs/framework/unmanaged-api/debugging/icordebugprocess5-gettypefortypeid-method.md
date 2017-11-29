---
title: "Метод ICorDebugProcess5::GetTypeForTypeID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeForTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08c4b72b5b37d9e3a2a2e19bad9e79449906b495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="efdbc-102">Метод ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="efdbc-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="efdbc-103">Преобразует значение ICorDebugType идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="efdbc-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efdbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efdbc-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efdbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efdbc-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="efdbc-106">[in] Идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="efdbc-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="efdbc-107">[out] Указатель на адрес объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="efdbc-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efdbc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="efdbc-108">Remarks</span></span>  
 <span data-ttu-id="efdbc-109">В некоторых случаях методы, которые возвращают идентификатор типа могут вернуть значение null `COR_TYPEID` значение.</span><span class="sxs-lookup"><span data-stu-id="efdbc-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="efdbc-110">Если это значение передается как `id` аргумент, `GetTypeForTypeID` метода не удастся и возвращать `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="efdbc-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efdbc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="efdbc-111">Requirements</span></span>  
 <span data-ttu-id="efdbc-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efdbc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efdbc-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efdbc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efdbc-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efdbc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efdbc-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efdbc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdbc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="efdbc-116">See Also</span></span>  
 [<span data-ttu-id="efdbc-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="efdbc-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="efdbc-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="efdbc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
