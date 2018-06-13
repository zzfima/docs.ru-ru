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
ms.openlocfilehash: 90319886dfe149a3d2d76451c1a8526299cf5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401652"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="b5649-102">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="b5649-102">EnumImportTypes Method</span></span>
<span data-ttu-id="b5649-103">Выполняет перечисление всех типов в каждой области.</span><span class="sxs-lookup"><span data-stu-id="b5649-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5649-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5649-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5649-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5649-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b5649-106">Дескриптор для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="b5649-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="b5649-107">Максимальное число извлекаемых типов.</span><span class="sxs-lookup"><span data-stu-id="b5649-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="b5649-108">Получает маркеры не должно превышать типа `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="b5649-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="b5649-109">Получает фактическое число типов в `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="b5649-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5649-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5649-110">Return Value</span></span>  
 <span data-ttu-id="b5649-111">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b5649-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5649-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b5649-112">Requirements</span></span>  
 <span data-ttu-id="b5649-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="b5649-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5649-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b5649-114">See Also</span></span>  
 [<span data-ttu-id="b5649-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b5649-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b5649-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b5649-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b5649-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="b5649-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
