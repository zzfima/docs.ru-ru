---
title: Метод ICorDebugType2::GetTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="ceb4b-102">Метод ICorDebugType2::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="ceb4b-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="ceb4b-103">Возвращает [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для этого типа.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ceb4b-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ceb4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ceb4b-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="ceb4b-106">[out] Указатель на [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ceb4b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ceb4b-107">Return Value</span></span>  
 <span data-ttu-id="ceb4b-108">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="ceb4b-109">`HRESULT` Коды включают следующее:</span><span class="sxs-lookup"><span data-stu-id="ceb4b-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="ceb4b-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="ceb4b-110">Return code</span></span>|<span data-ttu-id="ceb4b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ceb4b-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="ceb4b-112">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-112">Method succeeded.</span></span> <span data-ttu-id="ceb4b-113">Метод извлеченные является допустимым [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ceb4b-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="ceb4b-114">Тип не был загружен.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="ceb4b-115">Тип не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceb4b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="ceb4b-116">Remarks</span></span>  
 <span data-ttu-id="ceb4b-117">Этот метод обеспечивает сопоставление из ICorDebugType, который представляет тип, который может быть или могут не быть загружены в среду выполнения с [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который служит непрозрачный дескриптор, определяет тип, загружена в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="ceb4b-118">Если тип, представляющий ICorDebugType еще не были загружены, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="ceb4b-119">Если тип не поддерживается, возвращается `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="ceb4b-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb4b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ceb4b-120">Requirements</span></span>  
 <span data-ttu-id="ceb4b-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb4b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb4b-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceb4b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceb4b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceb4b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceb4b-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb4b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb4b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ceb4b-125">See Also</span></span>  
 [<span data-ttu-id="ceb4b-126">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="ceb4b-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
