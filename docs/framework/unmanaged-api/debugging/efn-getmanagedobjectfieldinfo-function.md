---
title: Функция _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e7d031d4a4f4e67134f4b88f3e3ff47316ce3b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183148"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="24a75-102">Функция _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="24a75-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="24a75-103">Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.</span><span class="sxs-lookup"><span data-stu-id="24a75-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24a75-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24a75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24a75-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="24a75-106">[in] Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="24a75-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="24a75-107">[in] Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="24a75-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="24a75-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="24a75-108">szFieldName</span></span>  
 <span data-ttu-id="24a75-109">[in] Управляемый объект указатель на имя поля.</span><span class="sxs-lookup"><span data-stu-id="24a75-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="24a75-110">[out] Значение поля.</span><span class="sxs-lookup"><span data-stu-id="24a75-110">[out] The field value.</span></span> <span data-ttu-id="24a75-111">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="24a75-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="24a75-112">[out] Смещение от `objAddr` к полю.</span><span class="sxs-lookup"><span data-stu-id="24a75-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="24a75-113">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="24a75-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24a75-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="24a75-114">Remarks</span></span>  
 <span data-ttu-id="24a75-115">Если смещение равно 0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="24a75-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="24a75-116">Если отсутствует управляемый код в потоке в данный момент в контексте, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением сообщения 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="24a75-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24a75-117">Требования</span><span class="sxs-lookup"><span data-stu-id="24a75-117">Requirements</span></span>  
 <span data-ttu-id="24a75-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24a75-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a75-119">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="24a75-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="24a75-120">Версии платформы .NET framework:</span><span class="sxs-lookup"><span data-stu-id="24a75-120">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24a75-121">См. также</span><span class="sxs-lookup"><span data-stu-id="24a75-121">See also</span></span>

- [<span data-ttu-id="24a75-122">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="24a75-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
