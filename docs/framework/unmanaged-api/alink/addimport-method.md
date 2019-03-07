---
title: Метод AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 261d80caa43ec478d3a3a33acdebcc1bfcfde8cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500711"
---
# <a name="addimport-method"></a><span data-ttu-id="84424-102">Метод AddImport</span><span class="sxs-lookup"><span data-stu-id="84424-102">AddImport Method</span></span>
<span data-ttu-id="84424-103">Добавляет импортирует в сборку.</span><span class="sxs-lookup"><span data-stu-id="84424-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84424-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84424-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="84424-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84424-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="84424-106">Уникальный идентификатор сборки, которую необходимо дополнить.</span><span class="sxs-lookup"><span data-stu-id="84424-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="84424-107">Уникальный идентификатор, полученный из [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="84424-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="84424-108">Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="84424-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="84424-109">`dwFlags` передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="84424-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="84424-110">Указатель на маркер, который получает идентификатор для результирующего файла.</span><span class="sxs-lookup"><span data-stu-id="84424-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84424-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84424-111">Return Value</span></span>  
 <span data-ttu-id="84424-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="84424-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84424-113">Требования</span><span class="sxs-lookup"><span data-stu-id="84424-113">Requirements</span></span>  
 <span data-ttu-id="84424-114">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="84424-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84424-115">См. также</span><span class="sxs-lookup"><span data-stu-id="84424-115">See also</span></span>
- [<span data-ttu-id="84424-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="84424-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="84424-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="84424-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="84424-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="84424-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
