---
title: Перечисление ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 786ff6895383fc18dcfedb26fab344f80f04c1df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138211"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="cbc6e-102">Перечисление ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="cbc6e-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="cbc6e-103">Содержит значения, задают политику чтения PDB-файлов.</span><span class="sxs-lookup"><span data-stu-id="cbc6e-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbc6e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="cbc6e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="cbc6e-105">Members</span></span>  
  
|<span data-ttu-id="cbc6e-106">Член</span><span class="sxs-lookup"><span data-stu-id="cbc6e-106">Member</span></span>|<span data-ttu-id="cbc6e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cbc6e-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="cbc6e-108">Указывает, что отладчик всегда должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="cbc6e-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="cbc6e-109">Указывает, что отладчик должен считывать только PDB-файлы, связанные со сборками с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="cbc6e-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="cbc6e-110">Указывает, что отладчик никогда не должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="cbc6e-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbc6e-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="cbc6e-111">Remarks</span></span>  
 <span data-ttu-id="cbc6e-112">Перечисление `ESymbolReadingPolicy` используется с методом [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cbc6e-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc6e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cbc6e-113">Requirements</span></span>  
 <span data-ttu-id="cbc6e-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbc6e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc6e-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cbc6e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbc6e-116">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cbc6e-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbc6e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc6e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc6e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc6e-118">See also</span></span>

- [<span data-ttu-id="cbc6e-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="cbc6e-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
