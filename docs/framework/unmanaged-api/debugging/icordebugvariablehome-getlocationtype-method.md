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
ms.openlocfilehash: 5d33c917ab814083ec2f3a3f3de6bdc264d90b77
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791008"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="e6204-102">Метод ICorDebugVariableHome:: Жетлокатионтипе</span><span class="sxs-lookup"><span data-stu-id="e6204-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="e6204-103">Возвращает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="e6204-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6204-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6204-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6204-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6204-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="e6204-106">заполняет Указатель на тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="e6204-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="e6204-107">Дополнительные сведения см. в описании перечисления [вариаблелокатионтипе](variablelocationtype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="e6204-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6204-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e6204-108">Requirements</span></span>  
 <span data-ttu-id="e6204-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6204-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6204-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6204-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6204-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6204-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6204-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6204-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6204-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6204-113">See also</span></span>

- [<span data-ttu-id="e6204-114">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e6204-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="e6204-115">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="e6204-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
