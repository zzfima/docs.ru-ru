---
title: "Функция _EFN_GetManagedExcepStack"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edcd93bec29c6f0fef3b0bed4b8293efead3932d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="ce2c1-102">Функция _EFN_GetManagedExcepStack</span><span class="sxs-lookup"><span data-stu-id="ce2c1-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="ce2c1-103">Учитывая адрес объекта управляемого исключения, возвращает строковую версию трассировки стека, содержащейся внутри.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce2c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce2c1-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce2c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce2c1-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="ce2c1-106">[in] Клиент которого выполняется отладка.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="ce2c1-107">[in] Указатель на управляемый объект, производный от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="ce2c1-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="ce2c1-108">szStackString</span></span>  
 <span data-ttu-id="ce2c1-109">[out] Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="ce2c1-110">[out] Число символов в буфере строки.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce2c1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce2c1-111">Remarks</span></span>  
 <span data-ttu-id="ce2c1-112">Если нет управляемого кода в потоке в данный момент в контексте, функция возвращает значение HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="ce2c1-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce2c1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ce2c1-113">Requirements</span></span>  
 <span data-ttu-id="ce2c1-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce2c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce2c1-115">**Заголовок:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="ce2c1-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="ce2c1-116">**Версия платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce2c1-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2c1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ce2c1-117">See Also</span></span>  
 [<span data-ttu-id="ce2c1-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="ce2c1-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
