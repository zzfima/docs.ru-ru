---
title: Метод EmitAssembly
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2adf53d1e29fda077cdcf7b79891f6271993109
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787578"
---
# <a name="emitassembly-method"></a><span data-ttu-id="e2578-102">Метод EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="e2578-102">EmitAssembly Method</span></span>
<span data-ttu-id="e2578-103">Создает сборку.</span><span class="sxs-lookup"><span data-stu-id="e2578-103">Creates the assembly.</span></span> <span data-ttu-id="e2578-104">Вызывайте этот метод после закрытия всех остальных файлов, кроме файла сборки.</span><span class="sxs-lookup"><span data-stu-id="e2578-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="e2578-105">Не вызывайте этот метод при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="e2578-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2578-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2578-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2578-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2578-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e2578-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="e2578-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2578-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2578-109">Return Value</span></span>  
 <span data-ttu-id="e2578-110">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="e2578-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2578-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e2578-111">Requirements</span></span>  
 <span data-ttu-id="e2578-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="e2578-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2578-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e2578-113">See also</span></span>

- [<span data-ttu-id="e2578-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e2578-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e2578-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e2578-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e2578-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="e2578-116">ALink API</span></span>](index.md)
