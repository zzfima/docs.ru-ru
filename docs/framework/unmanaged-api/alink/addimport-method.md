---
title: Метод AddImport 1
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
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="addimport-method1"></a><span data-ttu-id="658c4-102">Метод AddImport 1</span><span class="sxs-lookup"><span data-stu-id="658c4-102">AddImport Method1</span></span>
<span data-ttu-id="658c4-103">Добавляет импортирует в сборку.</span><span class="sxs-lookup"><span data-stu-id="658c4-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="658c4-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="658c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="658c4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="658c4-106">Уникальный идентификатор сборки, которую необходимо дополнить.</span><span class="sxs-lookup"><span data-stu-id="658c4-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="658c4-107">Уникальный идентификатор, извлеченный из [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="658c4-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="658c4-108">Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="658c4-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="658c4-109">`dwFlags` передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="658c4-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="658c4-110">Указатель на маркер, который получает идентификатор для результирующего файла.</span><span class="sxs-lookup"><span data-stu-id="658c4-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="658c4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="658c4-111">Return Value</span></span>  
 <span data-ttu-id="658c4-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="658c4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658c4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="658c4-113">Requirements</span></span>  
 <span data-ttu-id="658c4-114">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="658c4-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658c4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="658c4-115">See Also</span></span>  
 [<span data-ttu-id="658c4-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="658c4-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="658c4-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="658c4-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="658c4-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="658c4-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
