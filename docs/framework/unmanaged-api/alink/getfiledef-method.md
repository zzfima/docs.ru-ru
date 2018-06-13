---
title: Метод GetFileDef
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b772ae37baed44b90e4f5420e0f7724201a56abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401815"
---
# <a name="getfiledef-method"></a><span data-ttu-id="fff3b-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="fff3b-102">GetFileDef Method</span></span>
<span data-ttu-id="fff3b-103">Извлекает фактический маркер FileDef, используемый в метаданных (в отличие от маркера, присвоенному ALink).</span><span class="sxs-lookup"><span data-stu-id="fff3b-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fff3b-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fff3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fff3b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fff3b-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="fff3b-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="fff3b-107">Токен, добавляемого файла как извлечен из AddFile метод или метод AddImport.</span><span class="sxs-lookup"><span data-stu-id="fff3b-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="fff3b-108">Получает маркер FileDef.</span><span class="sxs-lookup"><span data-stu-id="fff3b-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fff3b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fff3b-109">Return Value</span></span>  
 <span data-ttu-id="fff3b-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="fff3b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fff3b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fff3b-111">Requirements</span></span>  
 <span data-ttu-id="fff3b-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="fff3b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff3b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fff3b-113">See Also</span></span>  
 [<span data-ttu-id="fff3b-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="fff3b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fff3b-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="fff3b-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="fff3b-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="fff3b-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
