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
ms.openlocfilehash: b0e6250987997b8d1c833b7b33a985900510fb03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742135"
---
# <a name="emitassembly-method"></a><span data-ttu-id="0a3af-102">Метод EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="0a3af-102">EmitAssembly Method</span></span>
<span data-ttu-id="0a3af-103">Создает сборку.</span><span class="sxs-lookup"><span data-stu-id="0a3af-103">Creates the assembly.</span></span> <span data-ttu-id="0a3af-104">Этот метод следует вызывайте после закрытия всех остальных файлов за исключением файла сборки.</span><span class="sxs-lookup"><span data-stu-id="0a3af-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="0a3af-105">Не вызывайте этот метод при создании несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="0a3af-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3af-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a3af-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a3af-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a3af-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0a3af-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="0a3af-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a3af-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a3af-109">Return Value</span></span>  
 <span data-ttu-id="0a3af-110">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0a3af-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a3af-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0a3af-111">Requirements</span></span>  
 <span data-ttu-id="0a3af-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="0a3af-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3af-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3af-113">See also</span></span>

- [<span data-ttu-id="0a3af-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0a3af-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0a3af-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0a3af-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0a3af-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="0a3af-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
