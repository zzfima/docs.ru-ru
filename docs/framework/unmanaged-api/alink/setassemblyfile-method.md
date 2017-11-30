---
title: "Метод SetAssemblyFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyFile
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile
helpviewer_keywords: SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d83062db41b5fa1485555de40be0a39a65e0459a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="e5472-102">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="e5472-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="e5472-103">Назначает имя сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="e5472-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="e5472-104">Не предназначен для использования при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="e5472-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5472-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5472-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5472-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5472-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="e5472-107">Полное имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="e5472-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e5472-108">Указатель на [интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5472-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="e5472-109">Флаги, как определено в [перечисление AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="e5472-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="e5472-110">Указатель на идентификатор итоговой сборки.</span><span class="sxs-lookup"><span data-stu-id="e5472-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5472-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5472-111">Return Value</span></span>  
 <span data-ttu-id="e5472-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e5472-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5472-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e5472-113">Requirements</span></span>  
 <span data-ttu-id="e5472-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="e5472-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5472-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e5472-115">See Also</span></span>  
 [<span data-ttu-id="e5472-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e5472-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e5472-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e5472-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e5472-118">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="e5472-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
