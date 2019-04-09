---
title: Функция _EFN_GetManagedObjectName
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a95008d98436161ac919ef307273bc797519f15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080622"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="393a9-102">Функция _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="393a9-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="393a9-103">Получает имя типа с помощью предоставленного указателя управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="393a9-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="393a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="393a9-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="393a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="393a9-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="393a9-106">[in] Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="393a9-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="393a9-107">[in] Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="393a9-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="393a9-108">szName</span><span class="sxs-lookup"><span data-stu-id="393a9-108">szName</span></span>  
 <span data-ttu-id="393a9-109">[out] Имя типа.</span><span class="sxs-lookup"><span data-stu-id="393a9-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="393a9-110">[out] Доступное число символов в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="393a9-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="393a9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="393a9-111">Remarks</span></span>  
 <span data-ttu-id="393a9-112">Если отсутствует управляемый код в потоке в данный момент в контексте, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением сообщения 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="393a9-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="393a9-113">Требования</span><span class="sxs-lookup"><span data-stu-id="393a9-113">Requirements</span></span>  
 <span data-ttu-id="393a9-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="393a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="393a9-115">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="393a9-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="393a9-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="393a9-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="393a9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="393a9-117">See also</span></span>

- [<span data-ttu-id="393a9-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="393a9-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
