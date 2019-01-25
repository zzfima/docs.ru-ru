---
title: Метод SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 006360203518f74adb964634af52505a71d51473
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587103"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="61717-102">Метод SetAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="61717-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="61717-103">Назначает имя сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="61717-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="61717-104">Не для использования при создании несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="61717-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61717-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61717-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61717-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="61717-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="61717-107">Полное имя файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="61717-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="61717-108">Указатель на [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="61717-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="61717-109">Флаги, как определено в [перечисление AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="61717-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="61717-110">Указатель на идентификатор итоговой сборки.</span><span class="sxs-lookup"><span data-stu-id="61717-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61717-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61717-111">Return Value</span></span>  
 <span data-ttu-id="61717-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="61717-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61717-113">Требования</span><span class="sxs-lookup"><span data-stu-id="61717-113">Requirements</span></span>  
 <span data-ttu-id="61717-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="61717-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61717-115">См. также</span><span class="sxs-lookup"><span data-stu-id="61717-115">See also</span></span>
- [<span data-ttu-id="61717-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="61717-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="61717-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="61717-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="61717-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="61717-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
