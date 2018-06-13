---
title: Метод SetNonAssemblyFlags
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0399a135eddfd87342db63e107c8eea59a6e54d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401707"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="dae9c-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="dae9c-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="dae9c-103">Задает флаги, не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="dae9c-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dae9c-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dae9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dae9c-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="dae9c-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="dae9c-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dae9c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dae9c-107">Return Value</span></span>  
 <span data-ttu-id="dae9c-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="dae9c-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae9c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dae9c-109">Requirements</span></span>  
 <span data-ttu-id="dae9c-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="dae9c-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae9c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dae9c-111">See Also</span></span>  
 [<span data-ttu-id="dae9c-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="dae9c-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="dae9c-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="dae9c-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="dae9c-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="dae9c-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
