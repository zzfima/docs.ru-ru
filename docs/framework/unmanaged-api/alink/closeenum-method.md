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
ms.openlocfilehash: fd7d63596690e2a5d0bc26448884ec09ecd63231
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129523"
---
# <a name="closeenum-method"></a><span data-ttu-id="f7c87-102">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="f7c87-102">CloseEnum Method</span></span>
<span data-ttu-id="f7c87-103">Закрывает указанное перечисление и освобождает связанные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f7c87-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7c87-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c87-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7c87-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="f7c87-106">Дескриптор перечисления будет закрыта.</span><span class="sxs-lookup"><span data-stu-id="f7c87-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7c87-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f7c87-107">Return Value</span></span>  
 <span data-ttu-id="f7c87-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f7c87-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c87-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f7c87-109">Requirements</span></span>  
 <span data-ttu-id="f7c87-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="f7c87-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c87-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f7c87-111">See also</span></span>

- [<span data-ttu-id="f7c87-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f7c87-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f7c87-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f7c87-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f7c87-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="f7c87-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
