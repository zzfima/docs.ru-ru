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
ms.openlocfilehash: 6a561205602920123176bd421ca2ef1b601166c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426049"
---
# <a name="getfiledef-method"></a><span data-ttu-id="c616b-102">Метод GetFileDef</span><span class="sxs-lookup"><span data-stu-id="c616b-102">GetFileDef Method</span></span>
<span data-ttu-id="c616b-103">Извлекает фактический токен Филедеф, используемый в метаданных (в отличие от маркера, назначенного ALink).</span><span class="sxs-lookup"><span data-stu-id="c616b-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c616b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c616b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c616b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c616b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c616b-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="c616b-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="c616b-107">Токен добавленного файла, полученный из метода AddFile или метода AddImport.</span><span class="sxs-lookup"><span data-stu-id="c616b-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="c616b-108">Получает токен Филедеф.</span><span class="sxs-lookup"><span data-stu-id="c616b-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c616b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c616b-109">Return Value</span></span>  
 <span data-ttu-id="c616b-110">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c616b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c616b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c616b-111">Requirements</span></span>  
 <span data-ttu-id="c616b-112">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="c616b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c616b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c616b-113">See also</span></span>

- [<span data-ttu-id="c616b-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c616b-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c616b-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c616b-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c616b-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="c616b-116">ALink API</span></span>](index.md)
