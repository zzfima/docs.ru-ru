---
title: Метод SetAssemblyFile2
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d96881ce35dca1ee7a196507ef8d81a565eed82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741500"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="bc4ad-102">Метод SetAssemblyFile2</span><span class="sxs-lookup"><span data-stu-id="bc4ad-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="bc4ad-103">Задает имя и параметры новой сборки.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="bc4ad-104">Не вызывайте этот метод при создании несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4ad-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc4ad-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc4ad-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc4ad-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="bc4ad-107">Имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="bc4ad-108">[Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) интерфейс для этого файла.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="bc4ad-109">Параметры, представленный [перечисление AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bc4ad-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="bc4ad-110">Получает уникальный идентификатор для создаваемой сборки.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc4ad-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc4ad-111">Return Value</span></span>  
 <span data-ttu-id="bc4ad-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc4ad-113">Требования</span><span class="sxs-lookup"><span data-stu-id="bc4ad-113">Requirements</span></span>  
 <span data-ttu-id="bc4ad-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4ad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bc4ad-115">See also</span></span>

- [<span data-ttu-id="bc4ad-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="bc4ad-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bc4ad-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="bc4ad-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bc4ad-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="bc4ad-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
