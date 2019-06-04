---
title: Указатель функции FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef308b624525c3a139c892e6118a24d6adb6e14a
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490464"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="d4df2-102">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="d4df2-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="d4df2-103">Указывает на функцию, распространенные вызовы языка среды выполнения (CLR) чтобы указать, что инициализация либо началась или уже завершена.</span><span class="sxs-lookup"><span data-stu-id="d4df2-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="d4df2-104">Этот указатель функции был объявлен устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d4df2-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4df2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4df2-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d4df2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4df2-106">Remarks</span></span>  
 <span data-ttu-id="d4df2-107">Эта функция реализуется узлом.</span><span class="sxs-lookup"><span data-stu-id="d4df2-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4df2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d4df2-108">Requirements</span></span>  
 <span data-ttu-id="d4df2-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4df2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4df2-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4df2-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4df2-111">**Библиотека:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="d4df2-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d4df2-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4df2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4df2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d4df2-113">See also</span></span>

- [<span data-ttu-id="d4df2-114">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="d4df2-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="d4df2-115">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d4df2-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
