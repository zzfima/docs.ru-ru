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
ms.openlocfilehash: 057794fe524a0ee01f6f090ca7e11a4a4b523047
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124933"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="2cfe8-102">Перечисление ECustomDumpFlavor</span><span class="sxs-lookup"><span data-stu-id="2cfe8-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="2cfe8-103">Содержит значения, указывающие, какие элементы следует включать в пользовательское подмножество дампа кучи при сообщении об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2cfe8-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfe8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cfe8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="2cfe8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2cfe8-105">Members</span></span>  
  
|<span data-ttu-id="2cfe8-106">Член</span><span class="sxs-lookup"><span data-stu-id="2cfe8-106">Member</span></span>|<span data-ttu-id="2cfe8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2cfe8-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="2cfe8-108">Указывает, что дамп пользовательской кучи должен запускаться как Малый дамп и включать дополнительные данные, указанные любыми экземплярами [кустомдумпитем](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) , передаваемыми в один и тот же метод.</span><span class="sxs-lookup"><span data-stu-id="2cfe8-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="2cfe8-109">Указывает, что дамп пользовательской кучи должен собирать все данные состояния времени выполнения, которые не были выделены динамически.</span><span class="sxs-lookup"><span data-stu-id="2cfe8-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cfe8-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2cfe8-110">Remarks</span></span>  
 <span data-ttu-id="2cfe8-111">Параметр типа `ECustomDumpFlavor` передается методу [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2cfe8-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfe8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2cfe8-112">Requirements</span></span>  
 <span data-ttu-id="2cfe8-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cfe8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cfe8-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2cfe8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2cfe8-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2cfe8-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cfe8-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cfe8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfe8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2cfe8-117">See also</span></span>

- [<span data-ttu-id="2cfe8-118">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="2cfe8-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="2cfe8-119">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="2cfe8-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="2cfe8-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="2cfe8-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
