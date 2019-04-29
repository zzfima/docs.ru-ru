---
title: Перечисление ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1e69d9cbf39049e82803d2f7bc795cc9fd0b368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796010"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="bf3d6-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="bf3d6-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="bf3d6-103">Содержит значения, указывающие, какие элементы будут включены в подмножество пользовательских кучи дампа при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="bf3d6-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf3d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf3d6-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="bf3d6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bf3d6-105">Members</span></span>  
  
|<span data-ttu-id="bf3d6-106">Член</span><span class="sxs-lookup"><span data-stu-id="bf3d6-106">Member</span></span>|<span data-ttu-id="bf3d6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf3d6-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="bf3d6-108">Указывает, что дамп пользовательской кучи следует запустить от имени мини-дамп и включения дополнительных данных, указанной любым [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) экземпляров передается тот же метод.</span><span class="sxs-lookup"><span data-stu-id="bf3d6-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="bf3d6-109">Указывает, что дамп пользовательской кучи необходимо собрать все данные состояния среды выполнения, которые не были динамически выделены.</span><span class="sxs-lookup"><span data-stu-id="bf3d6-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf3d6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf3d6-110">Remarks</span></span>  
 <span data-ttu-id="bf3d6-111">Параметр типа `ECustomDumpFlavor` передается [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="bf3d6-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf3d6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bf3d6-112">Requirements</span></span>  
 <span data-ttu-id="bf3d6-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf3d6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf3d6-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bf3d6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf3d6-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf3d6-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf3d6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf3d6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3d6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bf3d6-117">See also</span></span>

- [<span data-ttu-id="bf3d6-118">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="bf3d6-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="bf3d6-119">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="bf3d6-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="bf3d6-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="bf3d6-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
