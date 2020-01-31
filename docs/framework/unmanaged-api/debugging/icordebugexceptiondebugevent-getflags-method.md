---
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782916"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="bdc6a-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="bdc6a-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="bdc6a-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="bdc6a-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdc6a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdc6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdc6a-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="bdc6a-106">заполняет Указатель на значение [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="bdc6a-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdc6a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="bdc6a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdc6a-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="bdc6a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc6a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bdc6a-109">Requirements</span></span>  
 <span data-ttu-id="bdc6a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdc6a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc6a-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdc6a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdc6a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdc6a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdc6a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc6a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc6a-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdc6a-114">See also</span></span>

- [<span data-ttu-id="bdc6a-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="bdc6a-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="bdc6a-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bdc6a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
