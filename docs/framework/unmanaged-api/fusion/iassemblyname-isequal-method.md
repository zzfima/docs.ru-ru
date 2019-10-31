---
title: Метод IAssemblyName::IsEqual
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134308"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="4fea6-102">Метод IAssemblyName::IsEqual</span><span class="sxs-lookup"><span data-stu-id="4fea6-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="4fea6-103">Определяет, равен ли заданный объект [IAssemblyName](iassemblyname-interface.md) данному `IAssemblyName`на основе указанных флагов сравнения.</span><span class="sxs-lookup"><span data-stu-id="4fea6-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fea6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fea6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fea6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fea6-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="4fea6-106">окне Объект `IAssemblyName`, с которым сравнивается этот `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="4fea6-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="4fea6-107">окне Побитовое сочетание значений [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) , влияющих на сравнение.</span><span class="sxs-lookup"><span data-stu-id="4fea6-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fea6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4fea6-108">Requirements</span></span>  
 <span data-ttu-id="4fea6-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fea6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fea6-110">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4fea6-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4fea6-111">**Версии .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fea6-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fea6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4fea6-112">See also</span></span>

- [<span data-ttu-id="4fea6-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4fea6-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="4fea6-114">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="4fea6-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
