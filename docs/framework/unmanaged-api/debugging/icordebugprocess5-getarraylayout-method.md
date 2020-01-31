---
title: Метод ICorDebugProcess5::GetArrayLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: ea7630efedb7b667dc58174eda0cb98d9f382cfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792391"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="ce133-102">Метод ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="ce133-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="ce133-103">Предоставляет сведения о структуре типов массивов.</span><span class="sxs-lookup"><span data-stu-id="ce133-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce133-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce133-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce133-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce133-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="ce133-106">окне Токен [COR_TYPEID](cor-typeid-structure.md) , указывающий массив, макет которого требуется.</span><span class="sxs-lookup"><span data-stu-id="ce133-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="ce133-107">заполняет Указатель на структуру [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) , содержащую сведения о макете массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="ce133-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce133-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="ce133-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce133-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ce133-109">Requirements</span></span>  
 <span data-ttu-id="ce133-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce133-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce133-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce133-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce133-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce133-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce133-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce133-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce133-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce133-114">See also</span></span>

- [<span data-ttu-id="ce133-115">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="ce133-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="ce133-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ce133-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
