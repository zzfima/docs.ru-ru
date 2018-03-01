---
title: "Метод AddFile 1"
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
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 943ff2901ee0888860941e86d589060de729907d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="096b9-102">Метод AddFile 1</span><span class="sxs-lookup"><span data-stu-id="096b9-102">AddFile Method1</span></span>
<span data-ttu-id="096b9-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="096b9-103">Adds files to the assembly.</span></span> <span data-ttu-id="096b9-104">Может также использоваться для создания несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="096b9-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096b9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="096b9-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="096b9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="096b9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="096b9-107">Уникальный идентификатор сборки, которую необходимо дополнить.</span><span class="sxs-lookup"><span data-stu-id="096b9-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="096b9-108">Полное имя файла для добавления.</span><span class="sxs-lookup"><span data-stu-id="096b9-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="096b9-109">Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="096b9-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="096b9-110">`dwFlags`передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="096b9-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="096b9-111">[Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейс, который будет использоваться для выдачи метаданных, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="096b9-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="096b9-112">Указатель на котором будет храниться уникальный идентификатор добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="096b9-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="096b9-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="096b9-113">Return Value</span></span>  
 <span data-ttu-id="096b9-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="096b9-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="096b9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="096b9-115">Requirements</span></span>  
 <span data-ttu-id="096b9-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="096b9-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096b9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="096b9-117">See Also</span></span>  
 [<span data-ttu-id="096b9-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="096b9-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="096b9-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="096b9-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="096b9-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="096b9-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
