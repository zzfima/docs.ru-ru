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
ms.openlocfilehash: d3490477f30cd1c0badaa9cfd71433a5bf9d7a99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738995"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="24c1b-102">\_EFN\_GetManagedObjectName Function</span><span class="sxs-lookup"><span data-stu-id="24c1b-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="24c1b-103">Получает имя типа с помощью предоставленного указателя управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="24c1b-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24c1b-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24c1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24c1b-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="24c1b-106">[in] Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="24c1b-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="24c1b-107">[in] Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="24c1b-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="24c1b-108">szName</span><span class="sxs-lookup"><span data-stu-id="24c1b-108">szName</span></span>  
 <span data-ttu-id="24c1b-109">[out] Имя типа.</span><span class="sxs-lookup"><span data-stu-id="24c1b-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="24c1b-110">[out] Доступное число символов в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="24c1b-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24c1b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="24c1b-111">Remarks</span></span>  
 <span data-ttu-id="24c1b-112">Если отсутствует управляемый код в потоке в данный момент в контексте, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением сообщения 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="24c1b-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24c1b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="24c1b-113">Requirements</span></span>  
 <span data-ttu-id="24c1b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24c1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c1b-115">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="24c1b-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="24c1b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c1b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c1b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="24c1b-117">See also</span></span>

- [<span data-ttu-id="24c1b-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="24c1b-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
