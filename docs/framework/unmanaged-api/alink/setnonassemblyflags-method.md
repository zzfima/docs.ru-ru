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
ms.openlocfilehash: 2dcb363a2a84b3c2e0438e45663b96d9a0f83f61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445556"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="22269-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="22269-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="22269-103">Устанавливает флаги, не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="22269-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22269-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22269-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="22269-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22269-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="22269-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="22269-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22269-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22269-107">Return Value</span></span>  
 <span data-ttu-id="22269-108">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="22269-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22269-109">Требования</span><span class="sxs-lookup"><span data-stu-id="22269-109">Requirements</span></span>  
 <span data-ttu-id="22269-110">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="22269-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22269-111">См. также</span><span class="sxs-lookup"><span data-stu-id="22269-111">See also</span></span>

- [<span data-ttu-id="22269-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="22269-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="22269-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="22269-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="22269-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="22269-114">ALink API</span></span>](index.md)
