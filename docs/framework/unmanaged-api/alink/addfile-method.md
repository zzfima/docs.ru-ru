---
title: Метод AddFile
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c04bc008d0279601e90d13e6a57c52a458fca1d7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967884"
---
# <a name="addfile-method"></a><span data-ttu-id="22369-102">Метод AddFile</span><span class="sxs-lookup"><span data-stu-id="22369-102">AddFile Method</span></span>
<span data-ttu-id="22369-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="22369-103">Adds files to the assembly.</span></span> <span data-ttu-id="22369-104">Может также использоваться для создания несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="22369-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22369-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22369-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22369-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="22369-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="22369-107">Уникальный идентификатор сборки, которую необходимо дополнить.</span><span class="sxs-lookup"><span data-stu-id="22369-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="22369-108">Полное имя файла для добавления.</span><span class="sxs-lookup"><span data-stu-id="22369-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="22369-109">Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="22369-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="22369-110">`dwFlags` передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="22369-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="22369-111">[Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейс, который будет использоваться для выдачи метаданных, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="22369-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="22369-112">Указатель, где будет храниться уникальный идентификатор добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="22369-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22369-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22369-113">Return Value</span></span>  
 <span data-ttu-id="22369-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="22369-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22369-115">Требования</span><span class="sxs-lookup"><span data-stu-id="22369-115">Requirements</span></span>  
 <span data-ttu-id="22369-116">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="22369-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22369-117">См. также</span><span class="sxs-lookup"><span data-stu-id="22369-117">See also</span></span>
- [<span data-ttu-id="22369-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="22369-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="22369-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="22369-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="22369-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="22369-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
