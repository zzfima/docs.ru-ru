---
title: Метод GetFileDef
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741889"
---
# <a name="getfiledef-method"></a><span data-ttu-id="ea94d-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="ea94d-102">GetFileDef Method</span></span>
<span data-ttu-id="ea94d-103">Получает фактический маркер FileDef, используемый в метаданных (в отличие от маркера, назначенный ALink).</span><span class="sxs-lookup"><span data-stu-id="ea94d-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea94d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea94d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea94d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea94d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ea94d-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="ea94d-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="ea94d-107">Токен добавленный файл как полученные от AddFile метод или метод AddImport.</span><span class="sxs-lookup"><span data-stu-id="ea94d-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="ea94d-108">Получает маркер FileDef.</span><span class="sxs-lookup"><span data-stu-id="ea94d-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea94d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ea94d-109">Return Value</span></span>  
 <span data-ttu-id="ea94d-110">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ea94d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea94d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ea94d-111">Requirements</span></span>  
 <span data-ttu-id="ea94d-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="ea94d-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea94d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ea94d-113">See also</span></span>

- [<span data-ttu-id="ea94d-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ea94d-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ea94d-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ea94d-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ea94d-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="ea94d-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
