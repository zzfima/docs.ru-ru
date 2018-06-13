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
ms.openlocfilehash: aed553a3a8d54b5229a122e76b61e3e58d4af3c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401970"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="7ddee-102">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="7ddee-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="7ddee-103">Назначает свойства на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="7ddee-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ddee-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ddee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ddee-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7ddee-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="7ddee-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7ddee-107">Файл, определяющий свойство.</span><span class="sxs-lookup"><span data-stu-id="7ddee-107">File that defines the property.</span></span> <span data-ttu-id="7ddee-108">Может иметь значение NULL, если `AssemblyID` не указывает на несвязанный NETMODULE-файл.</span><span class="sxs-lookup"><span data-stu-id="7ddee-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="7ddee-109">Указывает возможность изменить.</span><span class="sxs-lookup"><span data-stu-id="7ddee-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="7ddee-110">Новое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="7ddee-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ddee-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7ddee-111">Return Value</span></span>  
 <span data-ttu-id="7ddee-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="7ddee-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ddee-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7ddee-113">Requirements</span></span>  
 <span data-ttu-id="7ddee-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="7ddee-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddee-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7ddee-115">See Also</span></span>  
 [<span data-ttu-id="7ddee-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="7ddee-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7ddee-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="7ddee-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7ddee-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="7ddee-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
