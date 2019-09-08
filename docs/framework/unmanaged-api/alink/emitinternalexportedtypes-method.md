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
ms.openlocfilehash: 04103ad305e0ae97669f3e07e06f03c2cdb4dfbd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787524"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="d94ca-102">Метод EmitInternalExportedTypes</span><span class="sxs-lookup"><span data-stu-id="d94ca-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="d94ca-103">Выдает типы, добавленные в сборку.</span><span class="sxs-lookup"><span data-stu-id="d94ca-103">Emits types added to the assembly.</span></span> <span data-ttu-id="d94ca-104">Вызовите этот метод после добавления известных внутренних типов.</span><span class="sxs-lookup"><span data-stu-id="d94ca-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d94ca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d94ca-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d94ca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d94ca-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d94ca-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="d94ca-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d94ca-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d94ca-108">Return Value</span></span>  
 <span data-ttu-id="d94ca-109">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="d94ca-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d94ca-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d94ca-110">Requirements</span></span>  
 <span data-ttu-id="d94ca-111">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="d94ca-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94ca-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d94ca-112">See also</span></span>

- [<span data-ttu-id="d94ca-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="d94ca-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d94ca-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="d94ca-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d94ca-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="d94ca-115">ALink API</span></span>](index.md)
