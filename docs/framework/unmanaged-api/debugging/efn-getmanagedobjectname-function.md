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
ms.openlocfilehash: c7333f8f7b95655ac821e9a2977d5db3794486a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123005"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="d023f-102">\_ЕФН\_функция Жетманажедобжектнаме</span><span class="sxs-lookup"><span data-stu-id="d023f-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="d023f-103">Возвращает имя типа, используя предоставленный указатель управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="d023f-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d023f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d023f-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d023f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d023f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="d023f-106">окне Указатель на клиент отладки.</span><span class="sxs-lookup"><span data-stu-id="d023f-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="d023f-107">окне Указатель на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="d023f-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="d023f-108">szName</span><span class="sxs-lookup"><span data-stu-id="d023f-108">szName</span></span>  
 <span data-ttu-id="d023f-109">заполняет Имя типа.</span><span class="sxs-lookup"><span data-stu-id="d023f-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="d023f-110">заполняет Число символов, доступных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="d023f-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d023f-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d023f-111">Remarks</span></span>  
 <span data-ttu-id="d023f-112">Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE с значением устройства 0x82 и кодом ошибки 0x1000.</span><span class="sxs-lookup"><span data-stu-id="d023f-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d023f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d023f-113">Requirements</span></span>  
 <span data-ttu-id="d023f-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d023f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d023f-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="d023f-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="d023f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d023f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d023f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d023f-117">See also</span></span>

- [<span data-ttu-id="d023f-118">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="d023f-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
