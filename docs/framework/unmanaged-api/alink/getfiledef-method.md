---
title: "Метод GetFileDef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetFileDef
api_location: alink.dll
api_type: COM
f1_keywords: GetFileDef
helpviewer_keywords: GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a31dee6bb1af4f555211822a3b7ec108353214a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="5bb83-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="5bb83-102">GetFileDef Method</span></span>
<span data-ttu-id="5bb83-103">Извлекает фактический маркер FileDef, используемый в метаданных (в отличие от маркера, присвоенному ALink).</span><span class="sxs-lookup"><span data-stu-id="5bb83-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bb83-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bb83-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bb83-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5bb83-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="5bb83-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="5bb83-107">Токен, добавляемого файла как извлечен из AddFile метод или метод AddImport.</span><span class="sxs-lookup"><span data-stu-id="5bb83-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="5bb83-108">Получает маркер FileDef.</span><span class="sxs-lookup"><span data-stu-id="5bb83-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bb83-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5bb83-109">Return Value</span></span>  
 <span data-ttu-id="5bb83-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5bb83-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb83-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5bb83-111">Requirements</span></span>  
 <span data-ttu-id="5bb83-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="5bb83-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb83-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb83-113">See Also</span></span>  
 [<span data-ttu-id="5bb83-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="5bb83-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5bb83-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="5bb83-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5bb83-116">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="5bb83-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
