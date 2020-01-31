---
title: Интерфейс ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: e90952a92c408762a98a2bfcb91b6aeb72052df1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791221"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="7a653-102">Интерфейс ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="7a653-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="7a653-103">Расширяет интерфейс ICorDebugType для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.</span><span class="sxs-lookup"><span data-stu-id="7a653-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a653-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7a653-104">Methods</span></span>  
  
|<span data-ttu-id="7a653-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7a653-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="7a653-106">Метод GetTypeID</span><span class="sxs-lookup"><span data-stu-id="7a653-106">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="7a653-107">Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.</span><span class="sxs-lookup"><span data-stu-id="7a653-107">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a653-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="7a653-108">Remarks</span></span>  
 <span data-ttu-id="7a653-109">Этот интерфейс является логическим расширением интерфейса ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="7a653-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a653-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7a653-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a653-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7a653-111">Example</span></span>  
 <span data-ttu-id="7a653-112">В следующем фрагменте кода показано использование метода [ICorDebugType2:: typeid](icordebugtype2-gettypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7a653-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="7a653-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7a653-113">Requirements</span></span>  
 <span data-ttu-id="7a653-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a653-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a653-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a653-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a653-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a653-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a653-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a653-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a653-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a653-118">See also</span></span>

- [<span data-ttu-id="7a653-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7a653-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
