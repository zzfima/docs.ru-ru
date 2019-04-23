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
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184500"
---
# <a name="getfiledef-method"></a><span data-ttu-id="16a7c-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="16a7c-102">GetFileDef Method</span></span>
<span data-ttu-id="16a7c-103">Получает фактический маркер FileDef, используемый в метаданных (в отличие от маркера, назначенный ALink).</span><span class="sxs-lookup"><span data-stu-id="16a7c-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16a7c-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="16a7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16a7c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="16a7c-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="16a7c-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="16a7c-107">Токен добавленный файл как полученные от AddFile метод или метод AddImport.</span><span class="sxs-lookup"><span data-stu-id="16a7c-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="16a7c-108">Получает маркер FileDef.</span><span class="sxs-lookup"><span data-stu-id="16a7c-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16a7c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16a7c-109">Return Value</span></span>  
 <span data-ttu-id="16a7c-110">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="16a7c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16a7c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="16a7c-111">Requirements</span></span>  
 <span data-ttu-id="16a7c-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="16a7c-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a7c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="16a7c-113">See also</span></span>

- [<span data-ttu-id="16a7c-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="16a7c-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="16a7c-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="16a7c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="16a7c-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="16a7c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
