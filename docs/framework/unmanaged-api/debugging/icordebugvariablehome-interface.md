---
title: Интерфейс ICorDebugVariableHome
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: c347346c9157fea843527c662e26ffcfba22ace4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790958"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="99a9f-102">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="99a9f-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="99a9f-103">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="99a9f-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99a9f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="99a9f-104">Methods</span></span>  
  
|<span data-ttu-id="99a9f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="99a9f-105">Method</span></span>|<span data-ttu-id="99a9f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="99a9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99a9f-107">Метод GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="99a9f-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="99a9f-108">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="99a9f-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="99a9f-109">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="99a9f-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="99a9f-110">Возвращает экземпляр "ICorDebugCode", который содержит этот объект `ICorDebugVariableHome`.</span><span class="sxs-lookup"><span data-stu-id="99a9f-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="99a9f-111">Метод GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="99a9f-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="99a9f-112">Возвращает собственный диапазон, в котором эта переменная находится в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="99a9f-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="99a9f-113">Метод GetLocationType</span><span class="sxs-lookup"><span data-stu-id="99a9f-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="99a9f-114">Возвращает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="99a9f-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="99a9f-115">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="99a9f-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="99a9f-116">Возвращает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="99a9f-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="99a9f-117">Метод GetRegister</span><span class="sxs-lookup"><span data-stu-id="99a9f-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="99a9f-118">Возвращает регистр, содержащий переменную с типом расположения `VLT_REGISTER`и базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="99a9f-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="99a9f-119">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="99a9f-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="99a9f-120">Возвращает управляемый индекс в виде слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="99a9f-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99a9f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="99a9f-121">Example</span></span>  
 <span data-ttu-id="99a9f-122">В следующем фрагменте кода используется объект [ICorDebugCode4](icordebugcode4-interface.md) с именем `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="99a9f-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="99a9f-123">Требования</span><span class="sxs-lookup"><span data-stu-id="99a9f-123">Requirements</span></span>  
 <span data-ttu-id="99a9f-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99a9f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99a9f-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99a9f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99a9f-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99a9f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99a9f-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99a9f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a9f-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="99a9f-128">See also</span></span>

- [<span data-ttu-id="99a9f-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="99a9f-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="99a9f-130">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="99a9f-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
