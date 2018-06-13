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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28f6bdbc3e382f82b7fdd632b9fc8c4d422629c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429739"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="76da6-102">Перечисление ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="76da6-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="76da6-103">Содержит значения, задать политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="76da6-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76da6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76da6-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="76da6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="76da6-105">Members</span></span>  
  
|<span data-ttu-id="76da6-106">Член</span><span class="sxs-lookup"><span data-stu-id="76da6-106">Member</span></span>|<span data-ttu-id="76da6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="76da6-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="76da6-108">Указывает, что отладчик должен всегда считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="76da6-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="76da6-109">Указывает, что отладчик должен считывать PDB-файлы, связанные с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="76da6-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="76da6-110">Указывает, что отладчик не должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="76da6-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76da6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="76da6-111">Remarks</span></span>  
 <span data-ttu-id="76da6-112">`ESymbolReadingPolicy` Перечисление используется с [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="76da6-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76da6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="76da6-113">Requirements</span></span>  
 <span data-ttu-id="76da6-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76da6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76da6-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76da6-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76da6-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76da6-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76da6-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76da6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76da6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="76da6-118">See Also</span></span>  
 [<span data-ttu-id="76da6-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="76da6-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
