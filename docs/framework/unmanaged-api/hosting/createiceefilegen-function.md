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
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136825"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="826e5-102">Функция CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="826e5-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="826e5-103">Создает объект [ицеефилежен](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="826e5-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="826e5-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="826e5-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="826e5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="826e5-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="826e5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="826e5-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="826e5-107">заполняет Указатель на адрес нового объекта `ICeeFileGen`.</span><span class="sxs-lookup"><span data-stu-id="826e5-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="826e5-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="826e5-108">Return Value</span></span>  
 <span data-ttu-id="826e5-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="826e5-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="826e5-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="826e5-110">Remarks</span></span>  
 <span data-ttu-id="826e5-111">Объект `ICeeFileGen` используется для создания переносимых исполняемых (PE) файлов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="826e5-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="826e5-112">Вызовите функцию [дестройицеефилежен](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) , чтобы уничтожить объект `ICeeFileGen` по завершении.</span><span class="sxs-lookup"><span data-stu-id="826e5-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="826e5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="826e5-113">Requirements</span></span>  
 <span data-ttu-id="826e5-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="826e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="826e5-115">**Заголовок:** Ицеефилежен. h</span><span class="sxs-lookup"><span data-stu-id="826e5-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="826e5-116">**Библиотека:** Мскорпе. dll</span><span class="sxs-lookup"><span data-stu-id="826e5-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="826e5-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="826e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826e5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="826e5-118">See also</span></span>

- [<span data-ttu-id="826e5-119">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="826e5-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
