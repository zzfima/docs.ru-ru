---
title: Метод EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e437868138d7ae31d233853ecc0f709de3ee39d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512727"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="4bdec-102">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="4bdec-102">EnumImportTypes Method</span></span>
<span data-ttu-id="4bdec-103">Перечисляет каждый тип в каждой области.</span><span class="sxs-lookup"><span data-stu-id="4bdec-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bdec-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bdec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bdec-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="4bdec-106">Дескриптор для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="4bdec-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="4bdec-107">Максимальное число извлекаемых типов.</span><span class="sxs-lookup"><span data-stu-id="4bdec-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="4bdec-108">Получает маркеры, не должно превышать типа `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="4bdec-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="4bdec-109">Получает фактическое число типов в `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="4bdec-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bdec-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4bdec-110">Return Value</span></span>  
 <span data-ttu-id="4bdec-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4bdec-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bdec-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4bdec-112">Requirements</span></span>  
 <span data-ttu-id="4bdec-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="4bdec-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bdec-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4bdec-114">See also</span></span>
- [<span data-ttu-id="4bdec-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="4bdec-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4bdec-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="4bdec-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4bdec-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="4bdec-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
