---
title: Метод CloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 70dca19075d8c896408ec78f89549b0c539280de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446577"
---
# <a name="closeassembly-method"></a><span data-ttu-id="6db2c-102">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="6db2c-102">CloseAssembly Method</span></span>
<span data-ttu-id="6db2c-103">Завершает операции сборки.</span><span class="sxs-lookup"><span data-stu-id="6db2c-103">Finalizes assembly operations.</span></span> <span data-ttu-id="6db2c-104">Вызовите этот метод перед началом новой сборки или несвязанного модуля.</span><span class="sxs-lookup"><span data-stu-id="6db2c-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db2c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6db2c-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6db2c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6db2c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6db2c-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="6db2c-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6db2c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6db2c-108">Return Value</span></span>  
 <span data-ttu-id="6db2c-109">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6db2c-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6db2c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6db2c-110">Requirements</span></span>  
 <span data-ttu-id="6db2c-111">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="6db2c-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db2c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="6db2c-112">See also</span></span>

- [<span data-ttu-id="6db2c-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="6db2c-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6db2c-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="6db2c-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6db2c-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="6db2c-115">ALink API</span></span>](index.md)
