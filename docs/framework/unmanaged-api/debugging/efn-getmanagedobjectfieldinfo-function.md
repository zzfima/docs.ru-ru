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
ms.openlocfilehash: dfa4db00662ed3abffbfd01e6e36005cd272a271
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664594"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="adaab-102">Функция _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="adaab-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="adaab-103">Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.</span><span class="sxs-lookup"><span data-stu-id="adaab-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adaab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adaab-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="adaab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="adaab-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="adaab-106">[in] Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="adaab-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="adaab-107">[in] Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="adaab-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="adaab-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="adaab-108">szFieldName</span></span>  
 <span data-ttu-id="adaab-109">[in] Управляемый объект указатель на имя поля.</span><span class="sxs-lookup"><span data-stu-id="adaab-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="adaab-110">[out] Значение поля.</span><span class="sxs-lookup"><span data-stu-id="adaab-110">[out] The field value.</span></span> <span data-ttu-id="adaab-111">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="adaab-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="adaab-112">[out] Смещение от `objAddr` к полю.</span><span class="sxs-lookup"><span data-stu-id="adaab-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="adaab-113">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="adaab-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adaab-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="adaab-114">Remarks</span></span>  
 <span data-ttu-id="adaab-115">Если смещение равно 0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="adaab-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="adaab-116">Если отсутствует управляемый код в потоке в данный момент в контексте, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением сообщения 0xa0 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="adaab-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adaab-117">Требования</span><span class="sxs-lookup"><span data-stu-id="adaab-117">Requirements</span></span>  
 <span data-ttu-id="adaab-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adaab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adaab-119">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="adaab-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="adaab-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adaab-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adaab-121">См. также</span><span class="sxs-lookup"><span data-stu-id="adaab-121">See also</span></span>
- [<span data-ttu-id="adaab-122">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="adaab-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
