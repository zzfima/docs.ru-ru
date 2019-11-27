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
ms.openlocfilehash: f2b78b35db6306c82e389955c4824875bcf25334
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447227"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="58cb1-102">Метод GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="58cb1-102">GetResolutionScope Method</span></span>
<span data-ttu-id="58cb1-103">Извлекает область заданного типа.</span><span class="sxs-lookup"><span data-stu-id="58cb1-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58cb1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="58cb1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58cb1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="58cb1-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="58cb1-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="58cb1-107">Файл, который необходим для ссылки.</span><span class="sxs-lookup"><span data-stu-id="58cb1-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="58cb1-108">Маркер файла, определяемый типом в, который обычно извлекается с помощью [метода ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="58cb1-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="58cb1-109">Получает ссылку на сборку или модуль.</span><span class="sxs-lookup"><span data-stu-id="58cb1-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58cb1-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="58cb1-110">Return Value</span></span>  
 <span data-ttu-id="58cb1-111">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="58cb1-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cb1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="58cb1-112">Requirements</span></span>  
 <span data-ttu-id="58cb1-113">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="58cb1-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cb1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="58cb1-114">See also</span></span>

- [<span data-ttu-id="58cb1-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="58cb1-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="58cb1-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="58cb1-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="58cb1-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="58cb1-117">ALink API</span></span>](index.md)
