---
title: Функция _EFN_GetManagedExcepStack
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e201b9a350c030da59e2b6ed27f84f570c8e621
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126663"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="08211-102">Функция _EFN_GetManagedExcepStack</span><span class="sxs-lookup"><span data-stu-id="08211-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="08211-103">Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.</span><span class="sxs-lookup"><span data-stu-id="08211-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08211-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08211-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08211-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08211-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="08211-106">[in] Клиент, для которого выполняется отладка.</span><span class="sxs-lookup"><span data-stu-id="08211-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="08211-107">[in] Указатель на управляемый объект, производный от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="08211-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="08211-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="08211-108">szStackString</span></span>  
 <span data-ttu-id="08211-109">[out] Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="08211-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="08211-110">[out] Доступное число символов в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="08211-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08211-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="08211-111">Remarks</span></span>  
 <span data-ttu-id="08211-112">Если отсутствует управляемый код в потоке в данный момент в контексте, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением сообщения 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="08211-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08211-113">Требования</span><span class="sxs-lookup"><span data-stu-id="08211-113">Requirements</span></span>  
 <span data-ttu-id="08211-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08211-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08211-115">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="08211-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="08211-116">Версии платформы .NET framework:</span><span class="sxs-lookup"><span data-stu-id="08211-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08211-117">См. также</span><span class="sxs-lookup"><span data-stu-id="08211-117">See also</span></span>

- [<span data-ttu-id="08211-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="08211-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
