---
title: "Метод AddImport 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d8827821deaeda311a42855737ecf53ab635a02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="e0e1b-102">Метод AddImport 1</span><span class="sxs-lookup"><span data-stu-id="e0e1b-102">AddImport Method1</span></span>
<span data-ttu-id="e0e1b-103">Добавляет импортирует в сборку.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0e1b-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0e1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0e1b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e0e1b-106">Уникальный идентификатор сборки, которую необходимо дополнить.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="e0e1b-107">Уникальный идентификатор, извлеченный из [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0e1b-108">Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="e0e1b-109">`dwFlags`передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0e1b-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e0e1b-110">Указатель на маркер, который получает идентификатор для результирующего файла.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0e1b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0e1b-111">Return Value</span></span>  
 <span data-ttu-id="e0e1b-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e0e1b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e1b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e0e1b-113">Requirements</span></span>  
 <span data-ttu-id="e0e1b-114">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="e0e1b-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e1b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e0e1b-115">See Also</span></span>  
 [<span data-ttu-id="e0e1b-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e0e1b-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e0e1b-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e0e1b-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e0e1b-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="e0e1b-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
