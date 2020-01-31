---
title: 'Метод ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790973"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="85f8b-102">Метод ICorDebugVariableHome:: GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="85f8b-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="85f8b-103">Возвращает управляемый индекс в виде слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="85f8b-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85f8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85f8b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85f8b-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="85f8b-106">заполняет Указатель на индекс в виде слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="85f8b-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85f8b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85f8b-107">Return Value</span></span>  
 <span data-ttu-id="85f8b-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="85f8b-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="85f8b-109">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="85f8b-109">Value</span></span>|<span data-ttu-id="85f8b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="85f8b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="85f8b-111">Вызов метода вернул значение индекса слота в `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="85f8b-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="85f8b-112">Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="85f8b-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85f8b-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="85f8b-113">Remarks</span></span>  
 <span data-ttu-id="85f8b-114">Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.</span><span class="sxs-lookup"><span data-stu-id="85f8b-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f8b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="85f8b-115">Requirements</span></span>  
 <span data-ttu-id="85f8b-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f8b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f8b-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85f8b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85f8b-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85f8b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85f8b-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f8b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f8b-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="85f8b-120">See also</span></span>

- [<span data-ttu-id="85f8b-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="85f8b-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
