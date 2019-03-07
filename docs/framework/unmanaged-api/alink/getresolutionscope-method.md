---
title: Метод GetResolutionScope
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfe06c1300a22757b363236454f4f494dab1978a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486801"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="79459-102">Метод GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="79459-102">GetResolutionScope Method</span></span>
<span data-ttu-id="79459-103">Извлекает область заданного типа.</span><span class="sxs-lookup"><span data-stu-id="79459-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79459-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79459-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="79459-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79459-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="79459-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="79459-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="79459-107">Файл, которому нужна ссылка.</span><span class="sxs-lookup"><span data-stu-id="79459-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="79459-108">Маркер файла, этот тип определен в, как правило, полученные с помощью [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="79459-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="79459-109">Получает сборку или ссылку на модуль.</span><span class="sxs-lookup"><span data-stu-id="79459-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79459-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79459-110">Return Value</span></span>  
 <span data-ttu-id="79459-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="79459-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79459-112">Требования</span><span class="sxs-lookup"><span data-stu-id="79459-112">Requirements</span></span>  
 <span data-ttu-id="79459-113">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="79459-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79459-114">См. также</span><span class="sxs-lookup"><span data-stu-id="79459-114">See also</span></span>
- [<span data-ttu-id="79459-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="79459-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="79459-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="79459-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="79459-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="79459-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
