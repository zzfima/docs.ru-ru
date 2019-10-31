---
title: Функция GetAssemblyIdentityFromFile
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134523"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="a7440-102">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="a7440-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="a7440-103">Возвращает указатель на объект `IUnknown` с указанным `IID` в сборке по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="a7440-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7440-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7440-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7440-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7440-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a7440-106">окне Допустимый путь к запрошенной сборке.</span><span class="sxs-lookup"><span data-stu-id="a7440-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="a7440-107">окне `IID` возвращаемого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a7440-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="a7440-108">заполняет Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a7440-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7440-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a7440-109">Requirements</span></span>  
 <span data-ttu-id="a7440-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7440-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7440-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a7440-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a7440-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7440-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7440-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a7440-113">See also</span></span>

- [<span data-ttu-id="a7440-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="a7440-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="a7440-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a7440-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
