---
title: Метод SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 589bd7b2132693c89dc10ae1a5c8d0bf52ed481e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218996"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="f7b96-102">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="f7b96-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="f7b96-103">Назначает свойства уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="f7b96-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7b96-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7b96-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7b96-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f7b96-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="f7b96-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f7b96-107">Файл, определяющий свойство.</span><span class="sxs-lookup"><span data-stu-id="f7b96-107">File that defines the property.</span></span> <span data-ttu-id="f7b96-108">Может иметь значение NULL, если `AssemblyID` не обеспечивает несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="f7b96-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="f7b96-109">Указывает, можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f7b96-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="f7b96-110">Новое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f7b96-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7b96-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f7b96-111">Return Value</span></span>  
 <span data-ttu-id="f7b96-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f7b96-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b96-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f7b96-113">Requirements</span></span>  
 <span data-ttu-id="f7b96-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="f7b96-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b96-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f7b96-115">See also</span></span>

- [<span data-ttu-id="f7b96-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f7b96-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f7b96-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f7b96-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f7b96-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="f7b96-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
