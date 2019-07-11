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
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742105"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="7db34-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="7db34-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="7db34-103">Выдает типы, добавленные к сборке.</span><span class="sxs-lookup"><span data-stu-id="7db34-103">Emits types added to the assembly.</span></span> <span data-ttu-id="7db34-104">Этот метод после известно, что внутренние типы были добавлены.</span><span class="sxs-lookup"><span data-stu-id="7db34-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db34-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7db34-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7db34-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7db34-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7db34-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="7db34-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7db34-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7db34-108">Return Value</span></span>  
 <span data-ttu-id="7db34-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="7db34-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7db34-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7db34-110">Requirements</span></span>  
 <span data-ttu-id="7db34-111">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="7db34-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db34-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7db34-112">See also</span></span>

- [<span data-ttu-id="7db34-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="7db34-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7db34-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="7db34-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7db34-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="7db34-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
