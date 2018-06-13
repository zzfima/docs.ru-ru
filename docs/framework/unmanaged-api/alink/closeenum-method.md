---
title: Метод CloseEnum
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5c3185dc6d488223d5882f543f0c690d82261b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402448"
---
# <a name="closeenum-method"></a><span data-ttu-id="3f209-102">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="3f209-102">CloseEnum Method</span></span>
<span data-ttu-id="3f209-103">Закрывает указанное перечисление и освобождает связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="3f209-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f209-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f209-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f209-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f209-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3f209-106">Дескриптор перечисления должен быть закрыт.</span><span class="sxs-lookup"><span data-stu-id="3f209-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f209-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3f209-107">Return Value</span></span>  
 <span data-ttu-id="3f209-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3f209-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f209-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3f209-109">Requirements</span></span>  
 <span data-ttu-id="3f209-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="3f209-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f209-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3f209-111">See Also</span></span>  
 [<span data-ttu-id="3f209-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3f209-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3f209-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3f209-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3f209-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="3f209-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
