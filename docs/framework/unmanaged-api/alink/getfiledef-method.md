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
ms.openlocfilehash: 5db205993bc1a0665dc0003948ce805813251f48
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787448"
---
# <a name="getfiledef-method"></a><span data-ttu-id="701f8-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="701f8-102">GetFileDef Method</span></span>
<span data-ttu-id="701f8-103">Извлекает фактический токен Филедеф, используемый в метаданных (в отличие от маркера, назначенного ALink).</span><span class="sxs-lookup"><span data-stu-id="701f8-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="701f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="701f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="701f8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="701f8-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="701f8-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="701f8-107">Токен добавленного файла, полученный из метода AddFile или метода AddImport.</span><span class="sxs-lookup"><span data-stu-id="701f8-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="701f8-108">Получает токен Филедеф.</span><span class="sxs-lookup"><span data-stu-id="701f8-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="701f8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="701f8-109">Return Value</span></span>  
 <span data-ttu-id="701f8-110">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="701f8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701f8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="701f8-111">Requirements</span></span>  
 <span data-ttu-id="701f8-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="701f8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701f8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="701f8-113">See also</span></span>

- [<span data-ttu-id="701f8-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="701f8-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="701f8-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="701f8-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="701f8-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="701f8-116">ALink API</span></span>](index.md)
