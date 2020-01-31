---
title: Метод ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790901"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="177e2-102">Метод ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="177e2-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="177e2-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="177e2-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="177e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="177e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="177e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="177e2-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="177e2-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="177e2-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="177e2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="177e2-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="177e2-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="177e2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="177e2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="177e2-109">Requirements</span></span>  
 <span data-ttu-id="177e2-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="177e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="177e2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="177e2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="177e2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="177e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="177e2-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="177e2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="177e2-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="177e2-114">See also</span></span>

- [<span data-ttu-id="177e2-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="177e2-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="177e2-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="177e2-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
