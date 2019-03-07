---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473474"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="6015e-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="6015e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="6015e-103">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="6015e-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6015e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6015e-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6015e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6015e-105">Parameters</span></span>  
  
|<span data-ttu-id="6015e-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="6015e-106">Parameter</span></span>|<span data-ttu-id="6015e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6015e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="6015e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6015e-108">Return Value</span></span>  
 <span data-ttu-id="6015e-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="6015e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6015e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6015e-110">Requirements</span></span>  
 <span data-ttu-id="6015e-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6015e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6015e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6015e-112">See also</span></span>
- [<span data-ttu-id="6015e-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="6015e-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
