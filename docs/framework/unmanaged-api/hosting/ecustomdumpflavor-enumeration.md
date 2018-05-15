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
ms.openlocfilehash: b6d0ba3f722f63650a3db6a8f633189993db0716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="4c15d-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="4c15d-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="4c15d-103">Содержит значения, указывающие, какие элементы будут включены в пользовательское подмножество кучи дампа при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4c15d-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c15d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c15d-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="4c15d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4c15d-105">Members</span></span>  
  
|<span data-ttu-id="4c15d-106">Член</span><span class="sxs-lookup"><span data-stu-id="4c15d-106">Member</span></span>|<span data-ttu-id="4c15d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4c15d-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="4c15d-108">Указывает, что дамп пользовательской кучи должен запустить как мини-дамп и содержать дополнительные данные, заданные любой [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) экземпляров, переданный в одном методе.</span><span class="sxs-lookup"><span data-stu-id="4c15d-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="4c15d-109">Указывает, что дамп пользовательской кучи необходимо собрать все данные состояния среды выполнения, которые не были выделены динамично.</span><span class="sxs-lookup"><span data-stu-id="4c15d-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c15d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c15d-110">Remarks</span></span>  
 <span data-ttu-id="4c15d-111">Тип параметра `ECustomDumpFlavor` передается [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4c15d-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c15d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4c15d-112">Requirements</span></span>  
 <span data-ttu-id="4c15d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c15d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c15d-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c15d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c15d-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c15d-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c15d-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c15d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c15d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4c15d-117">See Also</span></span>  
 [<span data-ttu-id="4c15d-118">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="4c15d-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="4c15d-119">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="4c15d-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="4c15d-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="4c15d-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
