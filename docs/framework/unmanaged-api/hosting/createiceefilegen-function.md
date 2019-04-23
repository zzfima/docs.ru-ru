---
title: Функция CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 566f73335861a8eb769b21a254e0e93b51a78d02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151818"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="80b57-102">Функция CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="80b57-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="80b57-103">Создает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="80b57-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="80b57-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80b57-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b57-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80b57-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80b57-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="80b57-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="80b57-107">[out] Указатель на адрес нового `ICeeFileGen` объекта.</span><span class="sxs-lookup"><span data-stu-id="80b57-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80b57-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80b57-108">Return Value</span></span>  
 <span data-ttu-id="80b57-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="80b57-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80b57-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="80b57-110">Remarks</span></span>  
 <span data-ttu-id="80b57-111">`ICeeFileGen` Объект используется для создания общего языка переносимого исполняемого (PE) файлов среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="80b57-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="80b57-112">Вызовите [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) функции для уничтожения `ICeeFileGen` объекта после завершения.</span><span class="sxs-lookup"><span data-stu-id="80b57-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80b57-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80b57-113">Requirements</span></span>  
 <span data-ttu-id="80b57-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80b57-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80b57-115">**Заголовок.** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="80b57-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="80b57-116">**Библиотека:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="80b57-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="80b57-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80b57-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b57-118">См. также</span><span class="sxs-lookup"><span data-stu-id="80b57-118">See also</span></span>

- [<span data-ttu-id="80b57-119">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="80b57-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
