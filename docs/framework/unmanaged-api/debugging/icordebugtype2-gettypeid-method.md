---
title: 'Метод ICorDebugType2:: TypeID'
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
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791230"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="a32a6-102">Метод ICorDebugType2:: TypeID</span><span class="sxs-lookup"><span data-stu-id="a32a6-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="a32a6-103">Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.</span><span class="sxs-lookup"><span data-stu-id="a32a6-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a32a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a32a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a32a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a32a6-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="a32a6-106">заполняет Указатель на [COR_TYPEID](cor-typeid-structure.md) для этого элемента ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="a32a6-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a32a6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a32a6-107">Return Value</span></span>  
 <span data-ttu-id="a32a6-108">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="a32a6-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="a32a6-109">Ниже приведены коды `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a32a6-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="a32a6-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="a32a6-110">Return code</span></span>|<span data-ttu-id="a32a6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a32a6-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="a32a6-112">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="a32a6-112">Method succeeded.</span></span> <span data-ttu-id="a32a6-113">Метод получил допустимый [COR_TYPEID](cor-typeid-structure.md).</span><span class="sxs-lookup"><span data-stu-id="a32a6-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="a32a6-114">Тип не был загружен.</span><span class="sxs-lookup"><span data-stu-id="a32a6-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="a32a6-115">Этот тип не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a32a6-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a32a6-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="a32a6-116">Remarks</span></span>  
 <span data-ttu-id="a32a6-117">Этот метод предоставляет сопоставление из объекта ICorDebugType, представляющего тип, который может быть или не загружен в среду выполнения, в [COR_TYPEID](cor-typeid-structure.md), который служит в качестве непрозрачного маркера, определяющего тип, загруженный в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="a32a6-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="a32a6-118">Если тип, который представляет объект ICorDebugType, еще не загружен, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="a32a6-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="a32a6-119">Если тип не поддерживается, он возвращает `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="a32a6-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a32a6-120">Требования</span><span class="sxs-lookup"><span data-stu-id="a32a6-120">Requirements</span></span>  
 <span data-ttu-id="a32a6-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a32a6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a32a6-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a32a6-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a32a6-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a32a6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a32a6-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a32a6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a32a6-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a32a6-125">See also</span></span>

- [<span data-ttu-id="a32a6-126">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="a32a6-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)
