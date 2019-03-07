---
title: Метод EmitInternalExportedTypes
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cee275dab33b847bb3a6e9839164615bdaa4a14
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502583"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="63fea-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="63fea-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="63fea-103">Выдает типы, добавленные к сборке.</span><span class="sxs-lookup"><span data-stu-id="63fea-103">Emits types added to the assembly.</span></span> <span data-ttu-id="63fea-104">Этот метод после известно, что внутренние типы были добавлены.</span><span class="sxs-lookup"><span data-stu-id="63fea-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63fea-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="63fea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="63fea-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="63fea-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="63fea-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63fea-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="63fea-108">Return Value</span></span>  
 <span data-ttu-id="63fea-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="63fea-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63fea-110">Требования</span><span class="sxs-lookup"><span data-stu-id="63fea-110">Requirements</span></span>  
 <span data-ttu-id="63fea-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="63fea-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fea-112">См. также</span><span class="sxs-lookup"><span data-stu-id="63fea-112">See also</span></span>
- [<span data-ttu-id="63fea-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="63fea-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="63fea-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="63fea-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="63fea-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="63fea-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
