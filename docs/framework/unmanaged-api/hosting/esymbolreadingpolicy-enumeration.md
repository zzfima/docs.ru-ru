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
ms.openlocfilehash: e17f88cf7f0d8572e65d00d8500a1fd83aa44eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663918"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="79b1a-102">Перечисление ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="79b1a-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="79b1a-103">Содержит значения, задавать политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="79b1a-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79b1a-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="79b1a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="79b1a-105">Members</span></span>  
  
|<span data-ttu-id="79b1a-106">Член</span><span class="sxs-lookup"><span data-stu-id="79b1a-106">Member</span></span>|<span data-ttu-id="79b1a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="79b1a-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="79b1a-108">Указывает, что отладчик должен всегда считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="79b1a-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="79b1a-109">Указывает, что отладчик должен считывать только PDB-файлы, которые связаны с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="79b1a-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="79b1a-110">Указывает, что отладчик не должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="79b1a-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79b1a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="79b1a-111">Remarks</span></span>  
 <span data-ttu-id="79b1a-112">`ESymbolReadingPolicy` Перечисление используется с [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="79b1a-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b1a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="79b1a-113">Requirements</span></span>  
 <span data-ttu-id="79b1a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b1a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b1a-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="79b1a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79b1a-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79b1a-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79b1a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79b1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b1a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="79b1a-118">See also</span></span>
- [<span data-ttu-id="79b1a-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="79b1a-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
