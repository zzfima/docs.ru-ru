---
title: 'Метод ICorDebugVariableHome:: Жетлокатионтипе'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 1dd4e9510831b4c878e9c1246dabe4add919130c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125114"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="0fc03-102">Метод ICorDebugVariableHome:: Жетлокатионтипе</span><span class="sxs-lookup"><span data-stu-id="0fc03-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="0fc03-103">Возвращает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="0fc03-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fc03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fc03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fc03-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="0fc03-106">заполняет Указатель на тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="0fc03-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="0fc03-107">Дополнительные сведения см. в описании перечисления [вариаблелокатионтипе](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0fc03-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc03-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0fc03-108">Requirements</span></span>  
 <span data-ttu-id="0fc03-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc03-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc03-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fc03-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fc03-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fc03-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fc03-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc03-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc03-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0fc03-113">See also</span></span>

- [<span data-ttu-id="0fc03-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="0fc03-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="0fc03-115">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="0fc03-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
