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
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446681"
---
# <a name="addfile-method"></a><span data-ttu-id="bc3d8-102">Метод AddFile</span><span class="sxs-lookup"><span data-stu-id="bc3d8-102">AddFile Method</span></span>
<span data-ttu-id="bc3d8-103">Добавляет файлы в сборку.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-103">Adds files to the assembly.</span></span> <span data-ttu-id="bc3d8-104">Также можно использовать для создания непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc3d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc3d8-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc3d8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc3d8-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bc3d8-107">Уникальный идентификатор сборки, подлежащая дополну.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="bc3d8-108">Полное имя добавляемого файла.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bc3d8-109">Флаги COM+ Филедеф, такие как `ffContainsNoMetaData` и `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="bc3d8-110">`dwFlags` передается в [метод дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="bc3d8-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="bc3d8-111">Интерфейс [IMetaDataEmit](../metadata/imetadataemit-interface.md) , используемый для выдачи метаданных при необходимости.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="bc3d8-112">Указатель на место, где будет храниться уникальный идентификатор добавленного файла.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc3d8-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc3d8-113">Return Value</span></span>  
 <span data-ttu-id="bc3d8-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc3d8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="bc3d8-115">Requirements</span></span>  
 <span data-ttu-id="bc3d8-116">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="bc3d8-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3d8-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc3d8-117">See also</span></span>

- [<span data-ttu-id="bc3d8-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="bc3d8-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bc3d8-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="bc3d8-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bc3d8-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="bc3d8-120">ALink API</span></span>](index.md)
