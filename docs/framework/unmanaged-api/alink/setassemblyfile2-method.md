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
ms.openlocfilehash: 41e10855a7254da4124ac0bf9aa247b90311632b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479090"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="67179-102">Метод SetAssemblyFile2</span><span class="sxs-lookup"><span data-stu-id="67179-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="67179-103">Задает имя и параметры новой сборки.</span><span class="sxs-lookup"><span data-stu-id="67179-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="67179-104">Не вызывайте этот метод при создании несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="67179-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67179-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67179-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="67179-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="67179-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="67179-107">Имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="67179-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="67179-108">[Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) интерфейс для этого файла.</span><span class="sxs-lookup"><span data-stu-id="67179-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="67179-109">Параметры, представленный [перечисление AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="67179-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="67179-110">Получает уникальный идентификатор для создаваемой сборки.</span><span class="sxs-lookup"><span data-stu-id="67179-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67179-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67179-111">Return Value</span></span>  
 <span data-ttu-id="67179-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="67179-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67179-113">Требования</span><span class="sxs-lookup"><span data-stu-id="67179-113">Requirements</span></span>  
 <span data-ttu-id="67179-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="67179-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67179-115">См. также</span><span class="sxs-lookup"><span data-stu-id="67179-115">See also</span></span>
- [<span data-ttu-id="67179-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="67179-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="67179-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="67179-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="67179-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="67179-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
